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


### ✔️Misson : 자판기 프로그램 
* 관리자가 커피 가격과 커피명을 정하고 개수를 입력한다.
* 소비자가 커피를 구매하는데 잔돈이 나와야 함
* 판매 종료 후 관리자가 커피 판매한 총액을 파악해야 함
* [작업진행중 별도 파일](https://github.com/jsKim-prog/pythonStudy24/blob/master/Mission_While.ipynb)
```
admin = {'id':'admin', 'pw': 'admin'} #관리자 계정
products = [] #상품들 넣을 리스트


intro ="""
==============
Coffee Time
==============
1. 커피구매
2. 자판기관리
3. Exit
==============
"""
promUser = f"""
======================
번호    종류     금액
======================
"""
promAdmin = """
1. 상품관리
2. 재고관리
3. 매상관리
4. Quit
"""
promSave = """
저장하시겠습니까? 
Yes : 1 / No : 2 / 종료 : 0
"""
promEnd = """
추가입력하시겠습니까? 
Yes : 1 / No : 2 
"""

def valAdmin(id, pw):
    result = True if id == admin.get('id') and pw == admin.get('pw') else False
    return result

class adminProm:
    def insertProd(name, price, stock):
        coffee = {
            'name': name,
            'price' : price,
            'stock' : stock
        }
        products.append(coffee)


class userProm:
    def userCoffeeSave(num): #커피 리스트에서 선택 커피 정보 받아오기
        userCoffee = products[num-1]
        #재고수량 검증
        if userCoffee.get('stock') <=0 : print("재고가 없습니다. 다른 커피를 선택하세요.")
        else : print("%s 커피를 선택하셨습니다." % userCoffee.get('name'))
        return userCoffee
    
    #돈 받기
    def selCoffee(insertMoney, userCoffee):
        total = int(userCoffee.get('price'))
        stockCnt = int(userCoffee.get('stock'))
        thisMoney = 0
        if insertMoney > total:
            print("%s 가 나옵니다~~ 즐거운 시간 되세요."% userCoffee.get('name'))
            print("거스름돈 받아가세요 : %d 원" % insertMoney-total)
             #수량변경할 리스트 찾기
            setIndex = products.index(userCoffee)
            setcoffee = products[setIndex]
            setcoffee['stock'] = stockCnt - 1
            return True
        elif insertMoney == total : 
           print("%s 가 나옵니다~~ 즐거운 시간 되세요."% userCoffee.get('name'))
            #수량변경할 리스트 찾기
           setIndex = products.index(userCoffee)
           setcoffee = products[setIndex]
           setcoffee['stock'] = stockCnt - 1
           return True 
        else:
            thisMoney += insertMoney
            print("투입금액 : %d 원" % thisMoney)
            print("추가 투입해야 할 금액 : %d 원" % total-thisMoney)      
            return False 


start = True
while start:
    print(intro)
    startNum = int(input("Enter Number>>> "))
    if startNum == 3:
        print("자판기를 종료합니다. 안녕히 가세요.")
        break
    elif startNum == 1:
        print(promUser)
        if len(products)<= 0 :
            print("등록된 상품이 없습니다. 다음에 다시 찾아주세요.")
        else:     
            for product in products:
                print("%d      %s      %d"% (products.index(product)+1,product.get('name'), product.get('price')))
            userNum = int(input("Enter Number>>> "))
            selectCoffee= userProm.userCoffeeSave(userNum)
            while userProm.selCoffee(inputMoney, selectCoffee):
                inputMoney = int(input("돈을 투입하세요.: "))
            
    elif startNum == 2 : 
        inputID = input("아이디 : ")
        inputPW = input("패스워드 : ")
        if valAdmin(inputID, inputPW):
            print(promAdmin)
            inputNum = int(input("Enter Number>>> "))
            match inputNum:
                case 1 : 
                    prodStart = True
                    while prodStart:
                        name = input("상품명 : ")
                        price = int(input("금액 : "))
                        stock = int(input("수량 : "))
                        print(promSave)
                        selnum = int(input("Enter Number>>> "))
                        if selnum==0:
                            prodStart=False
                            break
                        elif selnum==1:
                            adminProm.insertProd(name, price, stock)
                            print("상품이 저장되었습니다.") 
                            print(promEnd)
                            num1_1 = int(input("Enter Number>>> "))
                            if num1_1 == 2: 
                                prodStart=False
                                break
                        elif selnum==2:
                           pass
                        else:  print("잘못된 입력입니다. 다시 입력해 주세요.")
                case 2 : print("재고관리")
                case 3 : print("매상관리")
                case 4 : break
                case _ : print("잘못된 입력입니다. 다시 입력해 주세요.")

        else:    
            print("계정확인 필요")
    else:
        print("잘못된 입력입니다. 다시 입력해 주세요.")
        
```
