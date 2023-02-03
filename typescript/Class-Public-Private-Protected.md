# Public, Private, Protected In Class

- Public: 클래스 내부, 자식 클래스 내부, 클래스 인스턴스 전부 접근 가능함.
- Protected: 클래스 내부, 자식 클래스 내부에서 접근 가능. 클래스 인스턴스에서는 접근 불가.
- Private: 클래스 내부에서만 접근 가능. 자식 클래스 내부, 클래스 인스턴스에서는 접근 불가.

| Title            | Public | Protected | Private |
| ---------------- | ------ | --------- | ------- |
| 클래스 내부      | O      | O         | O       |
| 자식 클래스 내부 | O      | O         | X       |
| 클래스 인스턴스  | O      | X         | X       |

```ts
class Hello {
  public hello0(): string {
    return "hello0";
  }

  private hello1(): string {
    return "hello1";
  }

  protected hello2(): string {
    return "hello2";
  }
}

class BabyHello extends Hello {
  public hello3(): string {
    return this.hello1();
  }
}

const baby = new BabyHello();
console.log(baby.hello0()); // "hello0"
console.log(baby.hello1()); // Error
console.log(baby.hello2()); // Error
console.log(baby.hello3()); // Error
```
