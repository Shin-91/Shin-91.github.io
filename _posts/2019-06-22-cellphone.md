---
layout: post
title: 핸드폰 요금
---
# \[BOJ\] 1267 - 핸드폰 요금
[핸드폰 요금](https://www.acmicpc.net/problem/1267)  

<br>

기초적인 수학문제

`N` 개의 통화시간이 주어지고, 

1. 영식 요금제  
2. 민식 요금제   

  
두 요금제중 어떤 요금제를 사용하여야 요금이 적게 나오는 지 구하는 문제이다.

---


- 영식 요금제는 30초당 10원의 요금이 청구 (0~29 : 10원, 30~59 : 20원, 60~89 : 30원, ...)

- 민식 요금제는 60초당 15원의 요금이 청구 (0~59 : 15원, 60~119 : 30원, 120~179 : 45원, ...)

  
<span style="color:	#FF4500">

주어진 통화시간의 합에 대하여 얼마의 요금이 청구되는지 구하는 것이 아니라

  

각 통화시간에 대한 요금의 합을 구하는 것이다.

</span>

  

`N` 개의 통화시간 `P[i]`에 대해 요금은

  

영식 요금제는 $Y = (P[i] / 30 + 1) * 10$ 원

민식 요금제는 $M = (P[i] / 60 + 1) * 15$ 원

$\sum_{i=1}^N Y$ 와  $\sum_{i=1}^N M$
의 크기를 비교하여 출력하면 된다.

  

(`Y`와 `M`이 같을 경우 `Y`와 `M`을 한칸의 공백을 두고 출력한다, ex`Y M 45`)

  
``` cpp
#include <cstdio>
#include <iostream>
#include <vector>

using namespace std;

int n;
int y, m;

int main(void)
{
    scanf("%d", &n);
    for(int i=0;i<n;i++)
    {
        int a;
        scanf("%d", &a);
        y += (a/30 + 1)*10;
        m += (a/60 + 1)*15;
    }

    if(y < m)
        printf("Y %d\n", y);
    else if(y > m)
        printf("M %d\n", m);
    else
        printf("Y M %d\n", y);
}
```
