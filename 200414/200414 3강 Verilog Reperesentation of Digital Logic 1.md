# 200414 3강 Verilog Reperesentation of Digital Logic

![image-20200414155912892](200414%203%EA%B0%95%20Verilog%20Reperesentation%20of%20Digital%20Logic%201.assets/image-20200414155912892.png)

- c 언어와 심볼이 비슷함. - C언어 기반이기 때문



1. NOT GATE

   ![image-20200415153514777](200414%203%EA%B0%95%20Verilog%20Reperesentation%20of%20Digital%20Logic%201.assets/image-20200415153514777.png)

   - module = 함수 시작 이런느낌
   - 그림을 그린 후 -> 베릴로그 코딩!
   - out 출력 = ~A(INPUT)

![image-20200415153759415](200414%203%EA%B0%95%20Verilog%20Reperesentation%20of%20Digital%20Logic%201.assets/image-20200415153759415.png)

```verilog
module GATE( 
  input A,
  output out
  );
  wire A;
  wire out;
  assign out = ~A;
endmodule
```

- 내가 그린 회로를 verilog로 전달한다. (markup language)







2. OR GATE
   - 

![image-20200415154429024](200414%203%EA%B0%95%20Verilog%20Reperesentation%20of%20Digital%20Logic%201.assets/image-20200415154429024.png)



- ![image-20200415154501477](200414%203%EA%B0%95%20Verilog%20Reperesentation%20of%20Digital%20Logic%201.assets/image-20200415154501477.png)

- ```verilog
  module GATE(
    input A,
    input B.
    output out
    );
    wire A;
    wire B;
    wire out;
      
    assign out = A | B;
      
  endmodule
  ```





3. NOR GATE

   - ![image-20200415154724520](200414%203%EA%B0%95%20Verilog%20Reperesentation%20of%20Digital%20Logic%201.assets/image-20200415154724520.png)
   - NOR GATE가 기본적인 것이다.
   - BUT, verilog에는 NOR 게이트 표현식이 없기 때문에 ~(A|B)로 하게된다.(문법적으로 어쩔 수 없이)

   - NOT + NOT은 조합 제작 시 없어짐.

   - ```verilog
     module GATE(
         input A,
         input B,
         output out
     	);
     
         wire A;
         wire B;
         wire out
     
         assign out = ~(A|B);
     endmodule
             
     ```

   - netlist tool이 자동으로 최적화 해주면서 not+not을 없애줌.(optimization)

   - 그래서, cmos 회로를 생각하는게 중요하다.



4. NAND GATE
   - ![image-20200415155718316](200414%203%EA%B0%95%20Verilog%20Reperesentation%20of%20Digital%20Logic%201.assets/image-20200415155718316.png)
   - ![image-20200415155840650](200414%203%EA%B0%95%20Verilog%20Reperesentation%20of%20Digital%20Logic%201.assets/image-20200415155840650.png)
   - INPUT 이 0일 때 PMOS가 개통됨.
   - INPUT 이 1일 때 NMOS가 개통됨.

- propagation delay 도 역시 nand<and