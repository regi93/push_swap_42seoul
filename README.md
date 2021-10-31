# 프로젝트 소개

(짧은 영어실력과 번역기의 조합입니다... 반드시 원문을 보시길)



## Introduction



이 프로젝트는 매우 간단하고 효과적인 정렬 알고리즘 프로젝트이다. 아래 3가지 항목이 주어지고, 이것들을 이용하여 입력받은 정수 집합을 정렬하는 프로그램을 만들고 표춘 출력으로 출력한다.

* 정수값들의 집합
* 2개의 스택
* 2개의 스택을 조작하기 위한 명령어 집합



## Goals

* 정렬 알고리즘을 짜는 것은 항상 코더의 생에서 매우 중요한 단계이다. (complexity의 개념을 이때 처음 직면하는 경우가 많기 때문에)
* 정렬 알고리즘과 복잡도에 관한 질문은 취업 면접에서 단골 질문이다. 따라서 언젠가는 마주하게 될거다.. 그러니 개념을 잘 봐라
* 이 프로젝트의 학습 목표는 알고리즘, rigor(엄격함), C 언어의 사용이다. 특히 알고리즘의 복잡성!!
* 값을 정렬하는것은 간단하다. 가장 빠른 방법으로 정렬하는것은 덜 간단하다. 특히 초기값들의 순서에 따라 어떤 알고리즘을 적용하냐에 따라 결과(속도)가 달라진다.



## General Instructions

* 뮬리넷 없이 동료평가만으로 이루어진다. 파일 구성 및 이름은 자유롭지만 아래 규칙들을 지켜야한다.
* 실행 파일의 이름은 push_swap으로 해야한다.
* Makefile을 제출해야한다. (프로젝트를 컴파일하고, 기본 룰을 포함시킨, 그리고 프로그램이 필요시에만 재 컴파일 되도록)
* 영리하다면 프로젝트에 라이브러리를 넣고, libft 폴더와 그 안에 해당되는 Makefile을 넣어서 제출해야한다. 이때 Makefile은 프로젝트와 라이브러리를 모두 컴파일해야한다.
* 전역변수의 사용 금지
* C 언어 작성시 Norminette 준수할것
* 예외처리 및 에러에 대하여 세심하게 처리해야한다. (Segfalult, bus error, double free등..)
* 메모리 누수는 허용되지 않는다.
* Mandatory 파트에서 허용된 함수 : `wirte`, `read`, `malloc`, `free`, `exit`





## Mandatory

### Game Rules

* 게임은 `a` , `b`로 이름지어진 2개의 스택으로 구성된다.
* `a` 는 음수 , 양수로 이루어진 난수들이 담겨있다. (중복은 없다)

* `b` 는 비어있는 스택이다. 
* 목표는 오름차순으로 스택을 정렬하는 것이다.

* 아래 명령들을 이용해야 한다.



### swap operations

* `sa`  (swap - a) : 스택 `a`의 가장 위에 있는 두 원소(첫번째 원소, 두번째 원소)의 위치를 바꾼다.

* `sb`  (swap - b) : 스택 `b`의 가장 위에 있는 두 원소(첫번째 원소, 두번째 원소)의 위치를 바꾼다.

* `ss` :   `sa` `sb` 를 동시에 실행.



### push operations

* `pa`  (push - a) : 스택 `b` 의 가장 위에 있는 원소를 빼서 스택 `a` 의 가장 위에 삽입. (스택 `b`에 원소가 없다면, 아무동작도 이루어지지 않는다.)

* `pb` (push - b) : 스택 `a` 의 가장 위에 있는 원소를 빼서 스택 `b` 의 가장 위에 삽입. (스택 `a` 에 원소가 없다면, 아무동작도 이루어지지 않는다.)



### rotate operations

* `ra` (rotate a) : 스택 `a` 의 모든 원소들을 1칸씩 위로 올리고, 원래 맨 위에있던 원소는 맨 밑으로 옮긴다.
* `rb` (rotate b) : 스택 `b` 의 모든 원소들을 1칸씩 위로 올리고, 원래 맽 위에있던 원소는 맽 밑으로 옮긴다.
* `rr` : `ra` , `rb` 를 동시에 실행.

* `rra` (reverse rotate a) : `ra`  를 반대방향으로 실행한다. 즉, 1칸씩 모두 내리고 맨 밑의 원소는 맨위로 옮긴다.
* `rrb` (reverse rotate b) : `rb` 를 반대방향으로 실행한다.
* `rrr` : `rra` , `rrb` 를 동시에 실행.



## Example

![image-20211029152648704](/Users/yujun-yong/Library/Application Support/typora-user-images/image-20211029152648704.png)



## The "push_swap" program

* `push_swap` 이름으로 프로그램을 만들어라. 이 프로그램은 `a`에 들어갈 난수들을 정수리스트의 형태로 포맷팅하여 인자로 받는다. **첫 번째 인자가 스택의 맨위(탑)이 된다.**

* 프로그램은 스택 `a` 를 정렬하는데 필요한 가장 적은 명령어 리스트를 추력해야한다.

* 명령어들의 구분은 `\n` 만 허용된다.

* 에러 발생시 `"Error"` 와 개행을 출력해야한다. (에러 ex: 정수가 아닌 인자가 들어오거나, 정수 범위를 초과하거나, 중복이 있거나 ...)

  ![image-20211029153259005](/Users/yujun-yong/Library/Application Support/typora-user-images/image-20211029153259005.png)



* 디펜스 동안 , 제공하는 바이너리를 통해 프로그램을 체크해라.바이너리는 다음과 같이 동작할것이다.

![image-20211029153409453](/Users/yujun-yong/Library/Application Support/typora-user-images/image-20211029153409453.png)











