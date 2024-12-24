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

### ✔️DictionaryType : 딕셔너리 자료형 
* .get(key) : key에 해당하는 value 가져오기
*  in : 해당 Key가 딕셔너리 안에 있는지 조사하기


### ✔️SetType : 집합 자료형 
   
   | **구분** | **기호** | **함수**               |
   |:------:|:------:|:--------------------:|
   | 교집합    | s1 & s2 | s1.intersection(s2)  |
   | 차집합    | s1｜s2 | s1.union(s2)         |
   | 합집합    | s1 - s2 | s1.difference(s2)    |

### ✔️Misson : 자판기 프로그램 
* 관리자가 커피 가격과 커피명을 정하고 개수를 입력한다.
* 소비자가 커피를 구매하는데 잔돈이 나와야 함
* 판매 종료 후 관리자가 커피 판매한 총액을 파악해야 함
* [최종파일:링크 클릭](https://github.com/jsKim-prog/pythonStudy24/blob/master/Mission_While.ipynb)

### ✔️함수
* 매개변수(parameter) : 매개변수는 함수에 입력으로 전달된 값
* 인수(arguments) : 함수를 호출할 때 전달하는 입력값
  ```
  def add(매개변수1, 매개변수2):
  add(인수1, 인수2)
  ```
## 🧲 관례적 표현 모음  
* 변수명, 함수명 : _로 연결(java : funcName / python : func_name)

