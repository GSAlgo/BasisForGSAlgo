---
layout: post
title : 1.Introduction
author: JaeyunK
tags: [time complexity, sapce complexity, computation]
categories: Algorithm
use_math: true
---


이 교재?를 쓰는 사람(**JayunK**)은 문제를 푸는 것이 최고라고 생각을 한다.  

~~(그러면서 지가 더 안풀죠?)~~

JaeyunK는 설명을 하기 싫어서 본인이 생각하게 하는 것을 좋아하기 때문에, 설명은 거의 없이 교재를 만들려고 문제만 넣으려고 했다…

그러나 딱 봐도, 욕을 먹을거 같아서(...) 정답을 약간씩 넣어주면서 만들려고 한다.

(사실 성실하게 넣지는 않는다..)

추가로 이 교재를 쓰는 사람도 알고리즘을 잘 하는것은 아니니 이해 부탁한다. (^^)

무엇보다도 이 교재의 목적은 ”적어도 요건 알아야지…” 니깐? 가볍게 읽으면 된다! 

(그렇다고 모르면 곤난하다)

요약 : 내용을 너무 믿지는 말고, 알아둬서 손해보지는 않을 내용일 것이다?

> **Note:** 요새는 세상이 좋아져서 대학교 강의가 다 공개 되어 있으니 그걸 같이 듣는게 더 좋을듯…

> **Reference:** Erik Demaine, and Srini Devadas. _6.006 Introduction to Algorithms. _Fall 2011. Massachusetts Institute of Technology: MIT OpenCourseWare, [https://ocw.mit.edu](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011). License: [Creative Commons BY-NC-SA](https://creativecommons.org/licenses/by-nc-sa/4.0/). 

## Algorithm

`알고리즘`은 어떤 문제를 해결하는 방법을 일련의 절차나 방법을 공식화 한 것이다.

즉, 어떤 입력이 있을때, 알고리즘을 통해 출력으로 바꾸는 것이다.

`프로그램`과 `알고리즘`의 차이는 다음과 같이 설명할 수 있다.

`프로그램`을 만들기 위해서 우리는 `프로그래밍 언어`로 코드를 짜고, `알고리즘`을 만들기 위해서 `의사코드`라는 것을 작성하게 된다.

또, `프로그램`은 `컴퓨터`에서 돌아가는 반면, `알고리즘`은 `model of computation`에서 작동한다.



|        |      program       |       algorithm    |
|--------|--------------------|--------------------| 
|language|programming language|pseudo code         |
|machine |computer            |model of computation|




## model of computation

그렇다면, 우리가 알고리즘을 생각하기 위해서 만든 `model of computation`은 무엇일까?

model of computation은 알고리즘이 사용할 수 있는 `연산`들과 그 `비용`을 가지고 있는 것이다.

`Random Access Machine` (RAM)을 대표적인 예로 들 수 있는데, 흔히들 아는 RAM은 Random access memory의 약자로, 메모리의 임의의 위치의 공간에 접근, 조작, 저장을 상수시간에 할 수 있는 메모리를 뜻하고, Random Access Machine에서와 거의 같은 일을 한다. 

Random Access Machine은 



-  아주 큰 메모리 공간을 가지고 있고 임의의 메모리 공간에서
-   $\Theta(1)$ 시간에 $O(1)$ words를 불러오고, $O(1)$ 연산을 하며, $O(1)$ words를 저장할 수 있다. 
-   이때, `word`는 w bits를 의미한다.

> **Note:**  사실 몰라도 된다...




## 시간복잡도와 공간복잡도


### 일러두는 말

위에서 조금 이상한 말을 한 것 같겠지만, 복잡도를 이해하는데 큰 도움이 된다.


### Problems

다음 문제는 복잡도를 알아보기 위한 문제이다.


#### 1-1

1부터 n까지의 자연수의 합을 구하고 싶다. 컴퓨터를 이용해서 이 작업을 하려면 어떤 방법이 있을까?

<br/><br/><br/><br/><br/><br/>

#### 1-2

이 두 방법의 차이를 생각해보자.


``` c++
for(int i=1; i<=n; i++)
    sum += i;
```



``` c++
sum = n*(n+1)/2
```


> **Note:** 연산을 수행하는 횟수를 생각해보자

<br/><br/><br/><br/><br/><br/>

----

#### 2-1

n번째 피보나치수를 구하고 싶다. 어떻게 하면 될까?
> **Note:** 피보나치 수는 다음과 같은 점화식으로 만들어 진다 ~~(이건 상식)~~
>
> $$\begin{cases}
> F_1 = 1, \;\;\;\;\; F_2 = 1 \\
> F_{n+2} = F_{n+1} +  F_{n}    (n\in\mathbb{N})
>\end{cases} $$ 

<br/><br/><br/><br/><br/><br/>
#### 2-2

두 방법에서 차이를 생각해보자


``` c++
int fibo[MAX_N+1];
fibo[1] = fibo[2] = 1;
for(int i=3; i<=n; i++)
    fibo[i] = fibo[i-1] + fibo[i-2];
```



``` c++
int now_fibo = 1, before_fibo = 1;
for(int i=2; i<=n; i++){
    int temp = now_fibo;
    now_fibo = now_fibo + before_fibo;
    before_fibo = now_fibo;
}
```


> **Note:** 메모리(변수)를 얼마나 사용하는지 생각해보자


<br/><br/><br/><br/><br/><br/>

## 마무리 하면서

물론 당연하게도 뭔소리인지 잘 모르겠지만 끝까지 다 보고 다시 본다면 깨달음을 얻을 수 있지 않을까?

