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

