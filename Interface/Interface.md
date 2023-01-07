# 인터페이스 

 IT에서 인터페이스는 컴퓨터와 다른 주변기기를 연결하는 표준을 의미한다. 

 자바에서 인터페이스는 구체적인 구현 없이 기능만 선언한 클래스라고 한다.
 
 예시)
 
 Remote.java
 
 ```java 
    public interface Remote { //리모컨 인터페이스
    public void PowerOn();  // 전원켜기
    public void PowerOff();  // 전원 끄기 
    public void AddFunction();  // 추가기능 
 } 
```

Samsung.java

```java
  public class Samsung implements  Remote{
    @Override
    public void PowerOn() {
        System.out.println("삼성 티비를 켭니다.");
    }

    @Override
    public void PowerOff() {
        System.out.println("삼성 티비를 끕니다.");
    }

    @Override
    public void AddFunction() {
        System.out.println("음악듣기 기능이 있습니다.");
    }
 }
``` 

LG.java

```java
  public class LG implements remote{

    @Override
    public void PowerOn() {
        System.out.println("LG 티비를 켭니다.");
    }

    @Override
    public void PowerOff() {
        System.out.println("LG 티비를 끕니다.");
    }

    @Override
    public void AddFunction() {
        System.out.println("전화받기 기능이 있습니다.");
    }
 }
```

RemoteTest.java

```java
  public class RemoteTest {

    public static void main(String[] args) {

        Samsung samsung=new Samsung();
        samsung.PowerOn();
        samsung.AddFunction();
        samsung.PowerOff();

        LG lg=new LG();
        lg.PowerOn();
        lg.AddFunction();
        lg.PowerOff();
    }
  }
```

결과값 
```
삼성 티비를 켭니다.
음악듣기 기능이 있습니다.
삼성 티비를 끕니다.
LG 티비를 켭니다.
전화받기 기능이 있습니다.
LG 티비를 끕니다.
```

위의 코드는 리모컨의 예제이다. 

리모콘의 대표적인 기능은 티비 켜고 끄기가 있는데 

리모컨에 티비 켜고 끄는 메소드를 인터페이스 해놓고 

삼성이나 엘지에서 리모컨의 기능을 쓰게 된다. 

그 때의 인터페이스를 상속받게 되는데 그때는 extends 가 아니라

implements로 상속을 받아야한다.

받게 되면 그 기능들은 무조건 자식 클래스에서 구현을 해줘야한다.

즉, 인터페이스를 상속을 받게되면 받게 될 부모 클래스의 메소드를 무조건 

자식 클래스는 구현을 해줘야 한다.

이렇게 이해하기 힘들다면 

다른 예를 들수 있다.

동물에 대한 예를 들게 되면 

동물은 짓기와 움직이기가 어떠한 동물이든 한다. 

다만 그 동물이 어떤 동물인지에 따라서 짓는 소리가 다를것이고 움지이기 또한 다를것이다.

그럴때는 인터페이스를 동물로 생성 한 후 메소드만 생성한다. 

왜냐하면 모든 동물이 짓기가 "멍멍" 이라고 하지 않기 떄문에 

구현은 하지않고 그냥 짓기라는 메소드만 생성하는것이다.

그리고 난뒤 동물을 상속받을 대표적인 동물 강아지와 고양이 클래스 생성후 implements로 상속을 받고

각각의 동물에 해당하는 기능을 구현해주면 된다.

말로 설명한것을 코드 다시 한번 보게 되면  

``` java
  public interface 동물 {
     public void 짓기();
     public void 움직이기();
   
 }
```

```java
   public class 강아지 implements 동물{

    @Override
    public void 짓기() {
        System.out.println("멍멍");
    }

    @Override
    public void 움직이기() {
        System.out.println("푸다다다닥");
    }
  }
 ``` 

```java
   public class 고양이 implements 동물{

    @Override
    public void 짓기() {
        System.out.println("야옹");
    }

    @Override
    public void 움직이기() {
        System.out.println("사뿐사뿐");
    }
  }
 ``` 
 
 ```java
  public class 동물테스트 {

    public static void main(String[] args) {

       강아지 강아지 =new 강아지();
       강아지.짓기();
       강아지.움직이기();
       
       고양이 고양이=new 고양이();
       고양이.짓기();
       고양이.움직이기();
    }
  }
```

이렇게 구현을 할수 있다. (실제로 한글로 클래스와 메소드는 만들어도 실행은 되지만 않쓰는 것이 좋다.)
