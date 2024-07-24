### 프로토타입패턴의 샘플코드에 대해 수정한 경험

프로토타입패턴의 기본객체의 복사본을 생성하는 경우 클래스의 참조 타입을 복사하는 방법(얕은 복사, 깊은 복사) 중 깊은 복사를 통해 기존객체를 가리키지 않는 새로운 객체를 만들 때 사용하는 패턴

미리 정의된 값을 다른 객체에게 제공하는 경우에 유용합니다.

```swift
class MoonWorker {
    let name: String
    var health: Int = 100

    init(name: String) {
        self.name = name
    }

    func clone() -> MoonWorker {
        return MoonWorker(name: name)
    }
}

let prototype = MoonWorker(name: "Sam Bell")

var bell1 = prototype.clone()
bell1.health = 12

var bell2 = prototype.clone()
bell2.health = 23

var bell3 = prototype.clone()
bell3.health = 0
```

→ 샘플코드의 MoonWorker가 구조체로 작성되어있었는데 구조체는 기본적으로 값이 복사되기 때문에 프로토타입패턴을 사용할 필요가 없다고 생각하여 클래스타입으로 변경하도록 수정했습니다.
