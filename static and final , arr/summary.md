# static과 final/ 배열 

 > static 
 >  
 > > 필드나 메소드의 소속을 클래스로 제한하는 키워드 이다.
 > > 
 > > static을 사용한 정적 변수나 정적 메소드는 클래스 변수와 클래스 메소드 

예시)

Circle.java
``` java 
  
public class Circle {
    double radius;  //반 지름 ( 비정적 필드 -> 할당되는 객체마다 저장공간이 할당된다.)
    static double PI=3.14;  // 파이 ( 정적 필드 - > 클래스에 소속되 저장공간이 하나만 조재하는 변수이다.)

    public Circle(double radius){
        this.radius=radius;
    }
    // 원 넓이
    public double getArea(){
        return radius* radius *PI;
    }

    // 둘레
    public double getPerimeter(){
        return 2 *PI*radius;
    }
 }
```

CircleTest.java
```java 
public class CircleTest {
    public static void main(String[] args) {

        Circle c1=new Circle(10);
        System.out.println("원의 넓이: "+c1.getArea());
        System.out.println("원의 둘레: "+c1.getPerimeter());

        Circle c2=new Circle(100);
        System.out.println("원의 넓이: "+c2.getArea());
        System.out.println("원의 둘레: "+c2.getPerimeter());
     }
 }
```



 여기서 PI 같은 경우는 값이다. 
 
 그렇기 때문에 PI의 값을 new 라는 생성자로 메모리를 생성할 때마다 PI의 값을 잡히게 되면 
 
 메모리 관리를 효율적으로 사용을 하지못하게 된다. 

물론 지금은 하나 이기 떄문에 딱히 느끼는것이 없고 실행했을때 아무런 무리가 없지만 

100~200이상 이 되어버리면  8바이트 만큼 계속 메모리 공간에 쌓이게 된다.

컴퓨터의 자원은 무한정이지 않기 때문에 결국 메모리가 가득 차게 되어서 꺼지는 경우가 발생한다.

그렇기 떄문에 이러한 경우에는 "클래스 자체에만 가지고 있자!" 라고 해서 

static 을 붙여주게 되면 클래스 내에 공간만 갖게 된다.

즉, 쉽게 말하면 new 로 생성했을때 PI라는 공간을 각각 개인에게 가지게 되는것이 아니라 

 PI가 필요할때마다 클래스에 내에 있는 PI를 빌려(공유)쓴다는 것이다.
 
 그리고 static 같은 경우는 대문자로 쓴다.
