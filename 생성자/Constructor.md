# 생성자 

생성자 개요 

> 객체를 만드는 틀인 클래스에서 필요하면 생성자를 구현한다.
> 
> 객체가 생성될 때 필요한 작업을 수행하는 특별한 메소드이다.
> 
> 주로 객체 필드에 초기 값을 저장하거나 객체의 사용을 위해 필요한 초기화 작업이 수행된다.

생성자의 구성 

> 반환형을 기술하지 않으며 이름은 반드시 클래스 이름 사용 한다.
> 
>  생성자는 주요 접근 지정자를 public을 사용한다. (사용시 필요에 따라 접근 지정자 public 외에도 사용가능)
>  
>  기본 생성자는 내가 직접 만들지 않아도 자바에서 알아서 .

예시 

StudentTest.java 

``` java 
  public class StudentTest {

    public static void main(String[] args) {

      Student st1=new Student();  //기본 생성자
      st1.name="홍길동";

      Student st2=new Student("신덕균");

        System.out.println(st1.name);
        System.out.println(st2.name);
    }
 }
```
Student.java

```java
public class Student {
    String name;
 public Student(){
     System.out.println("학생 생성자가 호출되어짐");
 }

 public Student(String name){
     System.out.println("이름 파라미터를 갖는 학생 생성자가 호출되어짐.");
     this.name=name;
  }
 }
```

출력을하게 되면 

학생 생성자가 호출되어짐

이름 파라미터를 갖는 학생 생성자가 호출되어짐.

홍길동

신덕균

라는 결과가 나오게 된다. 

하지만 여기서 

 public Student(){
     System.out.println("학생 생성자가 호출되어짐");
 }
 
 에 주석을 달게 되면 에러가 뜬다. 기본 생성자가 없기 때문이다. 
 
 여기서 기본 생성자는 자바가 알아서 추가 해준다고 했는데 에러가 난다. 
 
 그 이유는 내가 임의대로 추가한 생성자가 생기게 되면 자바에서 기본 생성자를 추가 해 주지 않는다. 
 
 그러기 때문에 기본 생성자가  없다고 에러가 발생하게 된다.
 
 기본 생성자를 사용하기 위해서는 내가 직접 기본 생성자를 추가 해줘야 한다.
 <br>
 <br>
 
 > 즉, 다시 쉽게 말하면 결국 내가 생성자를 추가 하지 않는다 라면 자바에서는 "어? 너의 편리성을 위해서 내가 기본 생성자는 내가 추가해 놓을게" 라고 
 > 
 > 알아서 추가 해주지만 
 > 
 > 내가 생성자를 하나라도 추가 한다면 자바에서는 "너가 생성자를 만들었네?? 그러면 이왕 만드는 김에 기본 생성자도 너가 만들어" 라고 하면서 
 > 
 > 자바에서는 기본생성자를 알아서 추가해주지 않는다.
<br>
<br>
<br>
<br>
<br><br>


필요한 여러 생상자 구현 

> 생성자 오버로딩 
> 
> > 하나의 크래스에서 인자가 다르면 생성자를 여러 개 구현 가능하다.

 예시 
 Student.java 
 
 ``` java 
 public class Student {
    String name; // 이름
    int age; // 나이
    String gender; //성별
    String department;  //학과
 public Student(){

 }
 public Student(String name){
     this.name=name;
 }
 public Student(String name, int age){
     this.name=name;
     this.age=age;
 }
 public Student(String name,int age, String gender){
     this.name=name;
     this.age=age;
     this.gender=gender;
 }
 public Student(String name, int age,String gender, String department){
     this.name=name;
     this.age=age;
     this.gender=gender;
     this.department=department;
  }
 }
```

StudentTest.java
```java 
 public class StudentTest {

    public static void main(String[] args) {

      Student st1=new Student();  //기본 생성자
      Student st2=new Student("신덕균");
      Student st3=new Student("신덕균 ",25);
      Student st4=new Student("신덕균",25, "남자");
      Student st5=new Student("신덕균 ",25,"남자","정보통신공학과");


        System.out.println(st1.name+" "+st1.age+" "+st1.gender+" "+st1.department);
        System.out.println(st2.name+" "+st2.age+" "+st2.gender+" "+st2.department);
        System.out.println(st3.name+" "+st3.age+" "+st3.gender+" "+st3.department);
        System.out.println(st4.name+" "+st4.age+" "+st4.gender+" "+st4.department);
        System.out.println(st5.name+" "+st5.age+" "+st5.gender+" "+st5.department);
     }
 }
``` 

이러한 코드 형태를 생성자 오버로딩이다. 

오버로딩은 동일한 메스드에서 마라피터가 다른것을 오버로딩이라고 한다. 



