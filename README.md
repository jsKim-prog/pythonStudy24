![header](https://capsule-render.vercel.app/api?type=waving&height=120&color=gradient&text=pythonStudy24&fontColor=213555&fontSize=50&desc=파이썬%20AI%20기초%20학습용&descAlignY=84)
* MBC 아카데미 컴퓨터 교육센터 수원점에서 AI 기초 학습으로 파이썬 학습 진행용
* [점프 투 파이썬](https://wikidocs.net/book/1)

## 📁모듈 : mymod, mod1.py, modtest.py
* 파이썬 확장자 .py로 만든 파이썬 파일은 모두 모듈이다.
* 모듈을 쪼개는 이유는 큰 오류를 방지하기 위함

### ✔️모듈 불러오기
* 같은 디렉토리 모듈 불러오기
  ```
  import 모듈_이름
  ```
  ```
  from 모듈_이름 import 모듈_함수
  ```
* 다른 디렉토리 모듈 불러오기
  1. sys.path.append
     ```
     # 파이썬 쉘, cmd
     C:\doit>python
     >>> import sys
     >>> sys.path  #  파이썬 라이브러리가 설치되어 있는 디렉터리를 확인
     >>> sys.path.append("C:/doit/mymod") # import할 디렉토리 추가
     ```
   2. PYTHONPATH 환경 변수 사용
      ```
      C:\doit>set PYTHONPATH=C:\doit\mymod
      C:\doit>python
      >>> import mod2
      >>> print(mod2.add(3, 4))
      7
      ```
          
### ✔️if __name__ == "__main__"
* ```__name__``` : 파이썬이 내부적으로 사용하는 변수 이름
  - 직접 실행한 파일 : ```__main__```
  - 다른 모듈에서 import한 모듈의 경우 : ```모듈이름```


