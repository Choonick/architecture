# Composite 패턴

그릇과 내용물을 동일시 하여 디렉토리 구조와 같은 재귀적인 구조를 만들기 위한 디자인 패턴

클래스는 4가지로 나눠진다.

1. Main
2. Entry
3. Directory
4. File



## Entry Class

이름 - getName

크기 - getSize

디렉터리안에 파일이나 디렉터리를 추가하는 add()

printList - 종류를 나타내는 method (인수를 가진것, 안가진것)

toString 표준문자열 정의



## File Class

- 이름
- 크기
- printList(String)



## Directory Class

- 이름
- ArrayList
- add method
- getSize() 재귀적 호출
  - directory - 안의 엔트리의 크기를 하나하나 더한다.
  - file
- printList() 재귀적 호출

엔트리란?

