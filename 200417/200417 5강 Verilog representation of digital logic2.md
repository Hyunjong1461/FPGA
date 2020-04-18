# 200417 5강 Verilog representation of digital logic2

![image-20200417010036599](200417%205%EA%B0%95%20Verilog%20representation%20of%20digital%20logic2.assets/image-20200417010036599.png)

- wire와 reg의 차이
  - wire는 일종의 전선 -> 입력이 끝나는 순간 출력도 사라지게됨.
  - reg는 일종의 메모리
- 플립플롭에서는 reg의 키워드를 사용함
  - output signal에 사용

- D flip-flop은 신호는 두가지씩 !!
  - input -> 받아들이는 입장이기 때문에, 뭐로 받든 상관이 없음.(앞단의 로직에 의해 결정되기 때문..)
    - wire input
    - reg input
  - output
    - wire output -> 메모리 기능X -> combinational logic에서만 사용됨.
    - D의 입력이 사라지면 사라짐.
    - reg output -> 플립플롭의 출력은 항상 레지스터 (메모리 기능 수행해야함.)
    - D의 입력이 사라져도 사라지지 않음.

![image-20200417010840597](200417%205%EA%B0%95%20Verilog%20representation%20of%20digital%20logic2.assets/image-20200417010840597.png)

```verilog
  wire D;
  wire clock;
  output reg Q;
  output reg nQ;

always@(posedge clock) begin
    Q<=D;(순차적으로 실행 x)
    nQ<=~D;(동시 실행!!)
end


posedge clock->상승 클럭일 때만 올라가게 한다.
```



![image-20200417011307806](200417%205%EA%B0%95%20Verilog%20representation%20of%20digital%20logic2.assets/image-20200417011307806.png)

```verilog
#module이 상자
module D_FF( #시그널(신호) 정의
  input D,
  input clock,
  output Q,
  output nQ
  );
  #시그널의 특성을 정의해줌.
  #메모리 기능 x
  wire D;
  wire clock;
  #메모리 기능 o
  output reg Q;
  output reg nQ;

always@(posedge clock) begin
    Q<=D;(순차적으로 실행 x)
    nQ<=~D;(동시 실행!!)
end
endmodule
```



![image-20200417014422510](200417%205%EA%B0%95%20Verilog%20representation%20of%20digital%20logic2.assets/image-20200417014422510.png)

```verilog
module JK_FF(
	input J,
    input clock,
    input K,
    output Q,
    output NQ
);
wire J
wire clock
wire K
reg Q
reg NQ

#진리표를 보고 구현하면 좋다.
always@(posedge clock)begin
if(J==1'b0@@K==1'b0) begin
        
end else if(J==1'b0@@k==1'b1) begin
    if(Q==1'b1)begin
        Q<=~Q;
    end
end else if(J==1'b1@@k==1'b0) begin
    if(Q==1'b0)begin
        Q<=~Q;
    end
end else if(J==1'b1@@k==1'b1) begin
    Q<=~Q;
end else begin
end
endmodule
        
```

![image-20200417015527223](200417%205%EA%B0%95%20Verilog%20representation%20of%20digital%20logic2.assets/image-20200417015527223.png)

- 어차피 synthesis에서 툴이 최적화해주기 때문에, 차이가 나지는 않는다.
- but, 가독성이 좋아진다.



![image-20200417015637273](200417%205%EA%B0%95%20Verilog%20representation%20of%20digital%20logic2.assets/image-20200417015637273.png)

- A 또는 B의 로직이 바꼈을 때, always문이 실행된다.(둘 다)

- C,D 동시 실행 (바뀐 C가 작용되는 것이 아님.)

  