# 제네릭

> 제네릭은 일반적라는 의미로 코드를 여러 타입을 동시에 처리하는 기술이다. 
> 
>  다양한 종류의 데이터를 처리 할 수 있는 클래스와 메소드를 작성하는 기법이다.
>  
>  클래스를 정의할 때 클래스 안에서 사용하는 자료형을 구체적으로 명시하지 않고 T와 같은 기호로 표시한다.

예시 )

Box.java
```java 
   public class Box {
    private String data;
    public void setData(String data){
        this.data=data;
    }
    public String getData(){
      return data;
    }
  }
```

BoxTest.java

```java
   public class BoxTest {

    public static void main(String[] args) {

        Box box1=new Box();
        box1.setData("홍길동");

        String name=box1.getData();
        System.out.println(name);

        Box box2=new Box();
        box2.setData(25);
        Integer age=(Integer)box2.getData();
        System.out.println(age);
    }
  }
```

위에 코드에 Box 클래스는 어떠한 데이터를 담는 클래스이다.

그러면 box2의 객체에 나이를 넣기 위해서 25를 넣게 되면 에러가 발생한다. 

그러면 정수형을 담을 수있는 또 다른 클래스나 메소드를 만들어줘야 하는 상황이 발생한다. 

그것을 해결하고자 제네릭을 사용하는 것이다.

Box.java

```java
  public class Box<T> {
    private T data;

    public void setBox(T data){
        this.data=data;
    }

    public T getBox(){
        return data;
    }
 }
```

BoxTest.java

```java
  public class BoxTest {

    public static void main(String[] args) {

       Box<String> box1=new Box<>();
       box1.setBox("홍길동");
       String name=  box1.getBox();
        System.out.println(name);

        Box<Integer> box2=new Box<>();
        box2.setBox(25);
        Integer age= box2.getBox();
        System.out.println(age);
    }
 }
```

이렇게 제네릭을 사용하면 추가 생성을 해줄 필요가 없다 .

흐름을 조금 설명을 하자면 

main 메소드에서 객체를 생성할때 <String>이라고 생성이 되면 클래스에 접근 하는것이다.
  
그러면 Box 클래스에 <T>의 제네릭이 전부다 String으로 변경이 되는것이고 
  
다름 객체를 생성할때 <Integer>이라고 생성이 되면 

Box 클래스에 <T>의 제네릭이 전부다 Integer로 변경되는것이다.
  
그러면 강제 형변환도 해줄 필요도 없이 사용할 수 있다. 

<br>
<br>
<br>
   
   
### 타입 변수 표기법 
   
> 제네릭 클래스는 여러개의 타입 매개 변수를 가질 수 있으나 타입의 이름은 클래스나 인터페이스 내에서 유일해야 한다.
>
> 변수의 이름과 구분하기 위해서 한개의 대문자를 사용하며 타입 매개 변수는 기초 자료형으로 객체화될 수 없다.
> 
> > 예) E- Element / K-Key  / N - Number / T - Type / V - Value 등등
  
 
   
### 타입이 서로 다른 두 데이터 제네릭 
   
   Box2.java
   
```java 
   public class Box2<K ,V> {

    private K name;
    private V age;

    public void setData (K name, V age){
        this.name=name;
        this.age=age;
    }
    public K getName(){
        return name;
    }
    public V getAge(){
        return age;
    }
 }
```   
   BoxTest2.java
   
```java
   public class BoxTest2 {

    public static void main(String[] args) {

        Box2<String, Integer> box=new Box2<>();

        box.setData("홍길동",35);
        String name=box.getName();
        Integer age=box.getAge();

        System.out.println("이름: "+name +", 나이 : "+age);
    }
   }
``` 
   
<br>
<br>
<br>
   
### 제네릭 메소드 
   
> 일반 클래스의 메소드에서도 타입 매개 변수를 사용하여 제네릭 메소드를 정의 할 수 있다.

   GeMethod.java
   
```java 
   public class GeMethod {

    public <T> void print(T[] item){
        for (int i = 0; i <item.length ; i++) {
            System.out.println(item[i]);
        }
     }
  }
```
        
