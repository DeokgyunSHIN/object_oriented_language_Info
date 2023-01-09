# Math 클래스 

> Math 클래스는 수학계산 하는데 있어서 아주 유용하게 쓰이는 클래스이다. 
 
 Math.round(); --> 반올림 
 
 Math.ceil(); -->올림 
 
 Math.floor(); --> 버림 
 
 
예시) 
```java 
public class MathTest {

	public static void main(String[] args) {
		
		double d1=12.426;
		
		System.out.println(d1);
		System.out.println(Math.round(d1));  // 반올림  
		System.out.println(Math.ceil(d1));   // 올림 
		System.out.println(Math.floor(d1));    //버림 

	 }
 }
```

결과 
```
12.426
12
13.0
12.0
```

의 결과값이 나오는걸 알수 있다.


만약에 조건에서 

 반올림, 올림, 버림 을 소수점 둘째자리까지 표현해라 라고 하면 
 
 
 예시 )
 MathTest2.java 
 
  ```java 
  public class MathTest2 {

	public static double round(double d1, int n) {	
		return ((double)Math.round(d1 * Math.pow(10, n))) / Math.pow(10,n);
	}

	public static double ceil(double d1, int n) {
		return  ((double)Math.ceil(d1 * Math.pow(10, n))) / Math.pow(10,n);
	}

	public static double floor(double d1, int n) {
		return  ((double)Math.floor(d1 * Math.pow(10, n))) / Math.pow(10,n);
	}
  }
```

  MathTest.java
  
```java
  public class MathTest {

	public static void main(String[] args) {	
	double d1=12.426;
	
	System.out.println(d1);
	System.out.println(MathTest2.round(d1,2));  // 반올림  
	System.out.println(MathTest2.ceil(d1,2));   // 올림 
	System.out.println(MathTest2.floor(d1,2));    //버림 
	}
  }
```

실행한다면 

결과 
```
12.426
12.43
12.43
12.42
```

나오는걸 알수 있다.

코드 해석을 좀 하자면 Math.pow는 제곱을 한다는 뜻이다. 

Math.pow(a , b) ; 라고 한다면 a의 b승이라는 뜻이다. (a^b)

제곱을 곱해준 이유는 자릿수를 올려주기 위함이다. 

12.426 에서  n이 2이므로 10^2 는 100이 된다 .

12.426에서 100을 곱해주면 1242.6 이 되며 여기서  반올림, 올림, 버림을 

한 뒤에 다시 10^2 만큼 나눠주면 소수 둘째자리까지 표현이 가능하다느것을 알수 있다.
