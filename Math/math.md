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
