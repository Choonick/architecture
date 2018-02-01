springboot를 하려는데 new macbook 기본 java version이 java9 이었다.

downgrade하기 위해 java를 지웠다.

# mac java 지우기

```
sudo rm -rf /Library/Java/*

sudo rm -rf /Library/PreferencePanes/Java*

sudo rm -rf /Library/Internet\ Plug-Ins/Java*
```

삭제 확인은 ```java -version``` 으로 할 수 있다.

그리고 java8을 다시 설치해 주자

됬다 기쁘다. 하지만 삽질을 너무 많이 했다 공사장에서 일하는 것같았다.

맥을 사면 환경변수를 설정안해도 된다해서 좋을 줄 알았는데 메이븐을 설치할 때 해야한다...


#### /Users/jhoon
```
export PATH=$PATH:$M3_HOME/bin
export M3_HOME=/Users/jhoon/apache-maven-3.5.2

export M3=$M3_HOME/bin
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_151.jdk/Contents/Home

```

그리고 소스를 반영해준다.

```
source .profile
```


다시 오류가 난다.
그리고 난 화가 난다.

```
-bash: mvn: command not found
```

원인을 보니 source .profile을 하지 않으면 환경변수가 반영이 안된다.

... 됬다.

괜히 mysql 사용한다고 해놔서 오류났지만
pom.xml에서 mysql부분을 없애 문제를 해결했다.

### 그리고 코드를 수정하면 자동으로 빌드되도록 툴을 설치하기로 했다.
http://mvnrepository.com/artifact/org.springframework/springloaded/1.2.4.RELEASE

위의 링크에서 jar파일을 등록한다.