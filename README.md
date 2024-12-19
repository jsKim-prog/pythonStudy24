![header](https://capsule-render.vercel.app/api?type=waving&height=120&color=gradient&text=pythonStudy24&fontColor=213555&fontSize=50&desc=파이썬%20AI%20기초%20학습용&descAlignY=84)
* MBC 아카데미 컴퓨터 교육센터 수원점에서 AI 기초 학습으로 파이썬 학습 진행용
* [점프 투 파이썬](https://wikidocs.net/book/1)

### ✔️BaseType : 숫자형, 문자열 자료형
* 문자열 길이구하는 함수 : len(string)
* 예약어 출력 : 두번 연속 작성(%%, {{}}...)

### ✔️ListType : 리스트 자료형
1. create
   - a = []  / a = list()
1. read
   - sort()/reverse() : 오름차순/내림차순(리스트 요소를 정렬)
1. update
   - .append() : 이미 만들어진 리스트에 객체를 추가(뒤에 추가)
   - .insert(index, value) : 처음, 중간에 요소삽입 -> 삽입 후 기존 인덱스 재배치   
   - .extend(list) : 리스트 확장

    | List     	| Function        	| Result         	|
    |----------	|-----------------	|----------------	|
    | a=[1, 2] 	| **a.append(b)** 	| [1, 2, [3, 4]] 	|
    | b=[3, 4] 	| **a.extend(b)** 	| [1, 2, 3, 4]   	|

  1. delete
     -  del : 객체 삭제(ex : del a[2])
     -  .remove(value) : value 삭제(리스트 내 같은 값이 여러개인 경우 가장 앞쪽 인덱스의 값만 삭제 -> for문으로 전체 삭제)
     -  .pop(index) : 값 꺼내고 꺼낸 값 리스트에서 삭제
