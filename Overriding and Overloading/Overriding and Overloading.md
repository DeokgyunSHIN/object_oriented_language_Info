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
