# 4강_Digital Logic Review 2

- Sequential Logic
- D flip-flop
- JK flip-flop
- T flip-flop
- latch (NAND)



1. Sequential Logic

   - 과거의 입력/ 상태를 기억하는 디지털 로직
     - 출력 <= 현재 입력값 + 과거 입력 값(또는 상태)

   - 일반적으로 Clock에 Synchronous(동기)한 로직(synchronous sequential logic)

     - 출력 값을 결정하는 때

     - 입력 값에 변화가 생겼을 때 x(level - triggered)

     - Clock이 0 ->1로 Positive-edge일 때 o ( Edge - triggered) 

       

2. D-flip-flop

   ![image-20200415163409729](4%EA%B0%95_Digital%20Logic%20Review%202.assets/image-20200415163409729.png)

   - clk 가 0 -> 1이 변화하는 순간 data를 보내준다.

   - D의 입력을 Q의 출력으로 보내줌. -> 데이터를 저장한다.

   - 딜레이를 시킬 때도 사용됨.

     ![image-20200415163821924](4%EA%B0%95_Digital%20Logic%20Review%202.assets/image-20200415163821924.png)

   - SHIFT RESISTER

     - CLK의 WIRE 길이가 다르기 때문에, SKEW가 일어날 수 있다. (BUT, 강의에서는 무시)
     - CLK이 RISING EDGE일 경우 입력이 출력으로 전달된다.

     - 데이터의 값이 순서대로 밀린다.

     - 1이 입력이라면 한번 지나가면 Qa =1 Qb=0 Qc=0 Qd=0

     - 다시 0이 입력이라면 Qa=0 Qb=1 Qc=0 Qd=0

       

3.  JK flip-flop

   - ![image-20200415164732659](4%EA%B0%95_Digital%20Logic%20Review%202.assets/image-20200415164732659.png)

   - d와 다르게 입력이 2개임.

   - 클럭이 올라갈 때만 작동.

   - J= SET의 기능 , K= RESET의 기능

   - 1단계 j=1, K=0이기 때문에, SET의 기능 => Q=1

   - 2단계 J=0, K=1이기 때문에, RESET의 기능 => Q=0

   - 3단계 J=0, K=1이기 때문에, RESET의 기능 => Q=0

   - 4단계 J=1, K=1이기 때문에, 현재 출력값의 반전 => Q=1

   - 5단계 J=1, K=1이기 때문에, 현재 출력값의 반전 => Q=0

     

4.  T flip-flop

   - ![image-20200415165159225](4%EA%B0%95_Digital%20Logic%20Review%202.assets/image-20200415165159225.png)
   - j와 k를 T로 엮음.
   - 클럭이 들어올 때, T가 1이라면, 반전을 시켜준다.
   - 클럭이 들어올 때, T가 0이라면, J,K=0이므로 현재 상태를 유지시켜준다.





