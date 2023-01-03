# Getter와 Setter 

> Getter -> 필드의 값을 반환하는 메소드(즉,출력값 또는 리턴값이라고 생각하면 된다.)
> 
> Setter -> 필드의 값을 저장하는 메소드 
>
> Getter 와 Setter 는 무조건 쓰는것이 아닌 필드 접근 제한자가 :private 일때만 쓰인다. 
> 
> 이유는 private 은 외부에서 접근을 못하기 떄문에 접근을 하기 위해서는 getter와 setter의 메소드를 사용해서 데이터를 입력과 출력을 할수 있다.

예시 
``` java 
  public class Card {
    private  long cardNumber; // 카드번호(16자리 숫자)
  
    // setter
    public void setCardNumber(long cardNumber){
        this.cardNumber= cardNumber;
    }
    
    // getter 
    public long getCardNumber(){
        return cardNumber;
    } 
 }
```

그러고 난뒤 메소드 호출을 할떄는 setCardNumber(long 형 데이터) 또는 getCardNumber()를 사용하면 된다. 
