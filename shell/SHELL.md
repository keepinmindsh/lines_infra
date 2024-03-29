# Shell 이해하기 

## Index 

- Shell 
  - [ps](#ps)


## ps 

유닉스는 동시에 여러 개의 프로세서가 동작되기 때문에 사용자가 그것들의 목록과 상태를 점검할 필요가 있다.
ps 라는 이름은 processor status 를 의미한다. ps를 사용하여 프로세서들의 상태를 점검할 수 있다.

- command 

```shell
$ ps {Options}
```

- options 

``` 
-l : 자세한 형태의 정보를 출력한다. 
-u : 각 프로세서의 사용자 이름과 시작 시간을 보여준다. 
-j : 작업 중심 형태로 출력한다.
-s : 시그널 중심 형태로 출력한다.
-v : 가상 메모리 중심 형태로 출력한다.
-m : 메모리 정보를 출력한다. 
-a : 다른 사용자들의 프로세서도 보여준다.
-x : 로그인 상태에 있는 동안 아직 완료되지 않은 프로세서들을 보여준다. 
유닉스 시스템은 사용자가 로그아웃하고 난 후에도 임의의 프로세서가 계속 동작하게 할 수 있다. 그러면 그 프로세서는 자신을 실행시킨 셸이 없이도 계속 자신의 일을 
수행한다. 이러한 프로세서는 일반적인 ps 명령으로 확인할 수 없다. 이때 -x 옵션을 
사용하면 자신의 터미널이 없는 프로세서들을 확인할 수 있다. 
-S : 차일드(child) CPU 시간과 메모리 페이지 결함(fault) 정보를 추가 한다. 
-c : 커널 task_structure로 부터 명령 이름을 보여준다. 
-e : 환경을 보여준다. 
-w : 긴(wide) 형태로 출력한다. 한 행 안에 출력이 잘리지 않는다. 
-h : 헤더를 출력하지 않는다. 
-r : 현재 실행중인 프로세서를 보여준다.
-n : USER 와 WCHAN 을 위해 수치 출력을 지원한다.
```

### 참고 링크 ( 더 잘 정리되어 있어요~! )

> [https://wiper2019.tistory.com/195](https://wiper2019.tistory.com/195)