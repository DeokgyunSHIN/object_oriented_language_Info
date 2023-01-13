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

위의 코드를 고대로 실행을 하게 되면 에러가 발생하게 된다 .

그 이유는 조건 때문인데 

if(name.eqauls("홍길동"))를 해석을하면 

파라미터에서 받은 name이 "홍길동" 이라면 이라고 해석 할수 있다.

근데 이 조건에는 이 String 전재 조건이 인스턴스가 존재 할 때이다.

그렇게 떄문에 인스턴스가 존재하지 않을떄는(null) 에러가 발생하게 된다 .

그러면 이떄는 에러를 발생하지 않게 하기 위해서는 if문(조건문)을 바꿔주면 된다.

if("홍길동".eqauls(name)) 으로 변경해주면 에러가 발생하지 않게 된다.

즉, 비교할려고 하는 대상이 존재를 해야된다는 것이다. 

String name 이 "홍길동"과 같은가?  --------- 1번

"홍길동"이라는 문자열이 name가 같은가? 의 차이점이라고 생각하면 된다. ---------- 2번 

1번 같은 경우는 만약에 String name이 null 이 들어가버리면 비교를 할 대상이 없기 떄문에 에러를 발생하는것이다.

간혹 가다가  if(name!=null && str.equals("홍길동")) 이렇게 코드를 짜는 것을 볼수 있는데 

올바르지 않는 로직이다. 

만약에 여러분들이 파일이나 서류를 정리를 할때 조건을 두가지를 줬을 때 서류를 정리하는것과 

조건이 하나만 줬을 때 서류를 정리하는것은 속도 차이가 다르고 많이 까다로울 것이다.

컴퓨터 또한 똑같기 때문에 if(name!=null && str.equals("홍길동"))은 좋은 로직은 아니다.

<br>
<br>
<br>

### String 클래스 

> 자바에서 문자열을 처리하는 클래스이다.

```java
 public class StringTest {

     public static void p(Object o){
         System.out.print(o);
     }
     public static void pl(Object o){
         System.out.println(o);
     }

    public static void main(String[] args) {

      String s1="https://naver.com";

      final String FS="https://naver.com";

      //length()
        int length= s1.length();
        pl(length);

        //charAt()
        for (int i = 0; i <length; i++) {
            p(s1.charAt(i));
        }

        //toCharArray()
        pl("");
        for (char c1:s1.toCharArray()) {
            p(c1);
        }

        pl("");
        // contains(), indexOf(), lastIndexOf()
        pl(s1.contains("naver"));
        pl(s1.indexOf("naver"));
        pl(s1.lastIndexOf("naver"));

        //toLowerCase(), toUpperCase(), trim()
        pl(s1.toLowerCase());
        pl(s1.toUpperCase());
        pl(s1.trim());

        pl("");
        //contains(), indexOf(), lastIndexOf()
        pl(s1.contains("naver"));
        pl(s1.indexOf("naver"));
        pl(s1.lastIndexOf("naver"));

        //toLowerCase(), toUpperCase(), trim()
        pl(s1.toLowerCase());
        pl(s1.toUpperCase());
        pl(s1.trim());

        //equals(), equalsIgnoreCase()
        pl(s1.equals(FS));
        pl(s1.equalsIgnoreCase(FS));

        //split()
        String urls[]=s1.split("://");
        for (int i = 0; i <urls.length; i++) {
            System.out.println(urls[i]);
        }

        //replace(), replaceAll()
        pl(s1.replaceAll("com","co.kr"));
        pl(s1.startsWith("https"));
        pl(s1.endsWith("com"));

        //concat()
        pl(s1.concat("firstpage.do"));

        //substring()
        pl(s1.substring(10));

        //valueOf()
        String s2=String.valueOf("99");
        pl(s2);

        //comparTo()
        //같으면 0,
        pl(s1.compareTo(s2));
    } 
 }
```

