# 200414 2강 Digital Logic

1. 유의 사항
   - Combinational(and, or, not) vs Sequential(flip-flop)
   - when
   - Truth-table - 단순 암기 ㄴㄴ, 방심 ㄴㄴ -> 조금 어려워지면(시스템 복잡) 어려워함...
   - timing에 대한 특성을 추가적으로 이해하는 것도 필요



2. Combinational Logic

   - 입력측의 상태만을 가지고 출력 값이 결정되는 회로
   - 메모리기능이 필요없음

   

3. NOT GATE

   ![image-20200414024712595](200414%202%EA%B0%95%20Digital%20Logic.assets/image-20200414024712595.png)

   - 가장 적은 트랜지스터만을 가지고 구현할 수 있는 GATE
   - Input이 트랜지스터의 게이트에 연결됨
   - vdd는 pmos의 source-> gate에 0이 입력 되었을 때, source에서 drain으로 전류흐름.
   - -> output에 5v 출력됨.
   - gnd는 nmos의 source -> gate에 1이 입력 되었을 때, drain에서 source으로 전류흐름.
   - -> output에 0v 출력됨. (gnd와 output이 연결)
   - 신호의 전달이 빠름



4. OR GATE

   ![image-20200414025552257](200414%202%EA%B0%95%20Digital%20Logic.assets/image-20200414025552257.png)

   - Inverter = Not gate의 cmos 회로
   - logic마다 트랜지스터의 갯수가 다름 -> 소비전력이 달라짐 -> 시간적 요소 또한 달라짐.
   - stage가 하나 늘게됨.
   - propagation delay = input신호가 output단자까지 도달되는 시간
   - A=0, B=0일 때.
   - pmos는 0일 때 전류가 흐르게됨. -> vdd가 inverter에 입력(gate)단자로 입력됨.
   - nmos는 1일 때 전류가 흐르게됨. -> output이 0이됨

   

   ![image-20200414030500911](200414%202%EA%B0%95%20Digital%20Logic.assets/image-20200414030500911.png)

   - Timing diagram
   - logic의 변화와 타이밍에 관한 정보가 주어진다.
   - 타이밍 다이어그램이 복잡하면 헷갈릴 수 있음.
   - 인풋과 아웃풋이 무엇인지 인지하고 있어야함.



5. NOR GATE

   ![image-20200414030847621](200414%202%EA%B0%95%20Digital%20Logic.assets/image-20200414030847621.png)

   - OR + NOT이 붙었다 (X)

   - 실제로는 OR = NOR+NOT 이고, NOR은 PMOS 직렬 두개, NMOS 병렬 두개로 이루어져 있음.

   - 같은 면적이라면 OR보다 NOR의 갯수를 더 많이 사용할 수 있다.

     ![image-20200414031310429](200414%202%EA%B0%95%20Digital%20Logic.assets/image-20200414031310429.png)

6. NAND GATE

   - 트랜지스터 4개로 구현이된다. ( PMOS 병렬 2개, NMOS 직렬 2개 )

     ![image-20200414031538943](200414%202%EA%B0%95%20Digital%20Logic.assets/image-20200414031538943.png)

   - A=1 , B=1 일때

   - PMOS 두 개는 꺼지고, NMOS 두 개만 동작하므로 OUTPUT이 GND와 연결된다.

   - OUTPUT이 0이 출력되게 된다.

     ![image-20200414031850104](200414%202%EA%B0%95%20Digital%20Logic.assets/image-20200414031850104.png)

   

7. AND GATE

   - NAND + NOT GATE 로직의 결합으로 만들어짐.

   - NAND보다 복잡한 회로이다.

     ![image-20200414031754307](200414%202%EA%B0%95%20Digital%20Logic.assets/image-20200414031754307.png)

   ![image-20200414031815163](200414%202%EA%B0%95%20Digital%20Logic.assets/image-20200414031815163.png)

   - 둘다 입력이 HIGH 일 때만 출력이 1이 된다.

   

8. Sequential Logic

   - 입력측의 상태(현재) + 이전 상태(과거)를 가지고 출력 값이 결정됨.

   - 메모리 기능이 필요(과거의 값을 기억해야함.)
   - 메모리 역할을 한다.