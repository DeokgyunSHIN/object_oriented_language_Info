# 메소드 구현 

> 메소드(란 어떠한 특정 작업을 수행하기 위한 명령문의 집합이라 할 수 있다.
>
> 메소드의 정의는 
``` java
 접근제어자 반환타입 메소드이름(매개변수목록 또는 파라미터){ //선언부
   // 구현부
 }
```

> 로 이루어져 있다.
> 
> 예시) 

``` java 
public class Card {   //카드 클래스
    private long balance= 0; // 신용카드누적 사용금액
    private long point=0;  // 누적 포인드

    public void use(int amount){  // 신용카드 사용 메소드 (int 사용금액)
        balance+=amount;    //신용카드누적 사용금액+= 사용금액
    }
    public void payBill(int amount){  // 신용카드사용비용지급 메소드 (int 지급금액)
        balance-=amount;  // 신용카드누적 사용금액 -= 지급금액
        addPoint(amount);  //포인트지급 메소드 (지급금액)
    }
    public void addPoint(int amount){// 포인트 지급 메소드(int 지급금액)
        point+= amount * 0.01;  // 누적 포인드 += 지급금액 *0.01;
    }
 }
```
