# 오버라이딩과 오버로딩

### 오버라이딩 

> 상위 클래스의 동일한 메소드를 하위 클래스에서 다시 재정의 한다. 
> 
> 조건 
> 
> > 메소드의 반환 값과 메소드 이름, 매개변수는 반드시 같아야 한다.
> > 
> > 접근 지정자는 하위 클래스의 메소드가 보다 공개적이어야한다.
> > 
> > > 상위 클래스의 메소드가 public이면, 오버라이딩되는 메소드는 public 만 가능하다.
> > > 
> > > 상위 클래스의 메소드가 protected이면, 오버라이딩되는 메소드는 protected 만 가능하다.
> > > 
> > > 상위 클래스의 메소드가 default이면, 오버라이딩되는 메소드는 protected,default 만 가능하다.
> > > 
> > > 메소드 수정자가 fianl, private 인 메소드는 오버라이딩 할수 없다.

예시)

Vehicle.java

```java 
  public class Vehicle {

    void move(){
        System.out.println("차량이 움직인다.");
    } 
 }
```

Car.java

```java 
public class Car extends Vehicle{
    @Override
    void move(){
        System.out.println("부아아앙~");
    }
 }
```

Airplane.java

```java 
 public class Airplane extends Vehicle{
   @Override
    void move(){
        System.out.println("슈우우우욱~");
    }
 }
```

VehicleTest,java
```java 
 public class VehicleTest {
    public static void main(String[] args) {
        Vehicle vehicle=new Vehicle();
        Car car=new Car();
        Airplane airplane=new Airplane();

        vehicle.move();
        car.move();
        airplane.move();
    }
 }
```


결과값
```
 차량이 움직인다.
 부아아앙~
 슈우우우욱~
```

위의 코드를 보게 되면 상위 클래스(부모 클래스) 에서 상습받은 메소드를 하위 클래스(자식 클래스)에서 재정의 해서 사용할수 있다는 것을 알수 있다.

<br>
<br>
<br>

### 오버로딩 

> 클래스 내부에서 인자는 다르나 이름이 같은 메소드가 여러 개 정의 반환값은 다를 수 있짐나 , 인자가 같을 수는 없다.
> 
> 즉 ,좀더 쉽게 설명을 하면 메소드의 이름은 같고 매개변수(파라미터) 갯수나 타입이 다른 함수를 정의 하느 것을 말한다.

예제)

CalculatorTest.java

 ```java 
   public class CalculatorTest {
    public static void main(String[] args) {

        Calculator calculator=new Calculator();

        System.out.println(calculator.sum(10,20));
        System.out.println(calculator.sum(10,20,30));
        System.out.println(calculator.sum(10,20,30,40));
    }
 }
```

Calculator.java

 ```java
  public class Calculator {

    public int sum(int num1,int num2){
        return num1+num2;
    }
    public int sum(int num1,int num2, int num3){
        return num1+num2+num3;
    }
     public double sum(int num1, int num2,int num3,int num4){
        return (double) num1+num2+num3+num4;
    }
 }
```

예제코드를 보면 간단한 예제 코드를 만들었다.

오버로딩은 말 그래도 sum 의 메소드는 이름은 동일하나 파라메터 또는 매개변수는 달라야한다. -> 여기서 달라야 한다는 뜻은 

결국 갯수라든지 아니면 타입이 달라야 한다 .

즉 좀더 쉽게 설명은 하자면 

``` java 
   public int sum(int num1,int num2){
        return num1+num2;
    }
    public int sum(int num1, double num2){
        return num1+(int)num2;
    }
 ```
 
 위의 코드는 가능하다는말이다. 갯수는 같지만 타입이 다르기 떄문에 가능 하다 .
 
 |구분|오버로딩|오버라이딩|
 |:---:|:------:|:-----:|
 |메서드 이름| 동일 | 동일 |
 |매개변수,타입| 다름 |동일 |
 |리턴타입 | 상관없다.| 동일 |
 
 
 ### 최종 정리 
 
 > 오버로딩은 새로운 메소드르르 정의하는 것이며 
 > 
 > 오버라이딩은 상속받은 메소드를 재정의 하는것이다.
