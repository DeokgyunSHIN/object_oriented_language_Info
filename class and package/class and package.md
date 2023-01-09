# 자바 클래스 및 라이브러리 

### java.lang 패키지 

 > 자바 프로그램의 가장 기본이 되는 클래스들을 포함한다.
 > 
 > import문 없이 사용가능 하다.
 > 
 > > 대표적으로 String ,System 클래스를 import문 없이 사용 할 수 있다.

예시)

Sample.java

``` java
  import java.util.Calendar;
  import java.util.Date;

  public class Sample {

    public static void main(String[] args) {
        String str="홀길동";
        System.out.println(str);

        Date day= Calendar.getInstance().getTime();
    }
 }
```

위의 예시 코드를 보면 import가 선언되어져 있는걸 볼수 있다.

그러면 어? String 과 System은 import 선언 안된다면서요?

import를 보게 되면 마지막에 Calendar와 Date가 적혀있는걸 볼수 있을것이다.

그러면 즉, String과 System 때문에 import가 선언된 것이 아닌

Data 과 Calendar를 사용하기 위해서 import를 선언 한것이다.

그러면 import는 무슨 뜻일까??

쉽게 말하면 자바 내부 시스템에서 Date와 Calendar 파일이 여기에 있어요!! 라고 

알려주는 역할이라고 생각하면 된다.

만약에 import가 선언되지 않았을 때는 어떻게 될까?

Date과 Calendar에 빨간 밑줄이 그어진다.

거기에 마우스를 대면 import를 선언 하라 고 뜬다 .

그 뜻은 Data가 어디에 있는지 모르겠는데 혹시 여기에 있는거 맞니?? 맞으면 선언해줘~ 라고 

알려주는것이다.

### TMI

위에 코드를 보면 둘다 import.java.util 이 똑같다.

이 말은 java.util 파일에 있다는 것인데 하나 씩 하기 힘들떄는

import.java.util.*; 해주면 해결된다 .

"*" 는 java.util 파일은 전부 선언 하겠다! 라는 뜻이다.

<br>
<br>
<br>

### Object 클래스 

> 모든 클래스의 조상 클래스 이다. 따라서 Object 크래스의 멤버들은 상속이 가능하다면 다른 클래스에서도 사용 가능하다.

|메소드|기능|
|----|:----------------------:|
|clone| 객체 자신의 복사본을 리턴|
|equals| 객체 자신과 같은 객체인지를 리턴|
|finalize()|소멸될때 실행|
|getClass| 깨체 자신의 클래스 정보를 담고 있는 Class 인스턴스 반환|
|hashCode| 해시코드를 반환|
|toString|문자열 리턴|
|notify| 객체 자신을 사용하려고 기다리는 쓰레드를 하나만 깨운다|
|notifyAll| 객체 자신을 사용하려고 기다리는 모든 쓰레드를 꺠운다|


그중 가장 많이 쓰는것들을 좀더 다루자면 
<br>
<br>

### equals

> Object의 equals 메소드는 두 값을 비교한다.(참조변수 이기 때문에 주소값이 같은지를 비교한다.)
> 
> 이 말은 즉, 두 값이 가르키고 있는 메모리가 같은지를 확인하는것이다.
> 
> 보통 equals은 String 과 비교할때 많이 쓴다. 

예시)

HongildongTest.java

```java 
   public class HongildongTest {
    public  static boolean isHongildong(String name){
        if(name.equals("홍길동")){
            return true;
        }else{
            return false;
        }
    }

    public static void main(String[] args) {
        String str1="홍길동";
        String str2="이순신";
        String str3=null;

        System.out.println(isHongildong(str1));
        System.out.println(isHongildong(str2));
        System.out.println(isHongildong(str3));
    }
 }
```
