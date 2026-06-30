[DDD 예시 - Claude](https://claude.ai/chat/3fb89afc-0ecc-4038-8fd5-3ed5ba11099e)
- [[#Value Object]]
- [[#Entity]]
- [[#Aggregate]]
- [[#Repository]]
- [[#Domain Service]]
- [[#Domain Event]]

### Value Object
값으로 동일성을 판단, [[불변]] 객체
```ts
class Money {
  constructor(
    private readonly amount: number,
    private readonly currency: string
  ) {
    if (amount < 0) throw new Error("금액은 0보다 작을 수 없습니다");
  }
	
  add(other: Money): Money {
    if (this.currency !== other.currency) {
      throw new Error("통화가 다릅니다");
    }
    return new Money(this.amount + other.amount, this.currency);
  }
  
  equals(other: Money): boolean {
    return this.amount === other.amount && this.currency === other.currency;
  }
}
```

### Entity
식별자(ID)로 동일성을 판단하며, 상태가 변할 수 있음
```ts
class OtherItem {
  constructor(
    readonly id: string,
    readonly productId: string,
    private quantity: number,
    private readonly price: Money
  ) {}

  changeQuantity(newQuantity: number) {
    if (newQantity <= 0) throw new Error("수량은 1 이상이어야 합니다");
	this.quantity = newQuantity;
  }
  
  getSubtotal(): Money {
    return this.price.add(this.price).add(this.price);
  }
}
```

### Aggregate
연관된 엔티티/값 객체를 하나의 단위로 묶고,
Aggregate Root를 통해서만 외부에서 접근하도록 한다
```ts
class Order {
  private items: OrderItem[] = [];
  private status: "PENDING" | "CONFIRMED" | "CANCELLED" = "PENDING";
  
  constructor(readonly id: string, readonly customerId: string) {}
  
  addItem(item: OrderItem) {
    if (this.status !== "PENDING") {
	  throw new Error("이미 확정된 주문은 수정할 수 없습니다");
    }
	this.items.push(item);
  }
  confirm() {
    if (this.items.length === 0) {
	  throw new Error("최소 1개 이상의 상품이 필요합니다");
    }
    this.status = "CONFIRMED";
  }
}
```

### Repository
Aggregate 단위로 영속성(Persistence)을 다루는 인터페이스
```ts
interface OrderRepository {
  findById(id: string): Promise<Order | null>;
  save(order: Order): Promise<void>;
}
```

### Domain Service
하나의 엔티티에자연스럽게 속하지 않는 로직을 처리
```ts
class OrderPricingService {
  applyDiscount(order: Order, customer: Customer): MOney {
    // 여러 Aggregate(Order, Customer)를 조합한 로직
  }
}
```

### Domain Event
도메인에서 발생한 의미있는 사건을 표현
```ts
class OrderConfirmed {
  constructor(
    readonly orderId: string,
    readonly occuredAt: Date = new Date();
  ) {}
}
```











