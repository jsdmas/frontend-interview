# 목차

- 스택, 큐
- 배열
- 해쉬 맵
- 트리
- 복잡도, BigO

# ⭐ 스택과 큐의 차이점에 대해 설명해주세요.

> 스택과 큐의 가장큰 차이점은 데이터 추출 순서입니다.

## 스택(Stack)

- 데이터를 집어넣을 수 있는 선형(linear) 자료형입니다.
- **나중에 집어넣은 데이터가 먼저 나옵니다.(LIFO : Last In First Out)**
- 데이터를 집어넣는 `push`, 데이터를 추출하는 `pop`, 맨 나중에 집어넣은 데이터를 확인하는 `peek`등의 작업을 할 수 있습니다.
- 브라우저 뒤로가기, ctrl + z 등의 작업

> 스택은 서로 관계가 있는 여러 작업을 연달아 수행하면서 **이전의 작업 내용을 저장해 둘 필요가 있을 떄** 사용됩니다.

```js
class Stack {
  construtor() {
    this._arr = [];
  }
  push(item) {
    this._arr.push(item);
  }
  pop() {
    return this._arr.pop();
  }
  peek() {
    return this._arr[this._arr.length - 1];
  }
}

const stack = new Stack();
stack.push(1);
stack.push(2);
stack.push(3);
stack.pop(); // 3
```

## 큐(Queue)

- 데이터를 집어넣을 수 있는 선형(linear) 자료형입니다.
- **먼저 집어넣은 데이터가 먼저 나옵니다.(FIFO : First In First Out)**
- 데이터를 집어넣는 `enqueue`, 데이터를 추출하는 `dequeue`등의 작업을 할 수 있습니다.

> 큐는 **순서대로 처리해야 하는 작업을 임시로 저장해두는 버퍼(buffer)**로서 많이 사용됩니다.

```js
class Queue {
  construtor() {
    this._arr = [];
  }
  enqueue(item) {
    this._arr.push(item);
  }
  dequeue() {
    return this._arr.shift();
  }
}

const queue = new Queue();
queue.enqueue(1);
queue.enqueue(2);
queue.enqueue(3);
queue.dequeue(); // 1
```

# 좋은 알고리즘의 조건은 무엇인가요?

> 정확하게 처리하고 처리시간이 짧고 사용 메모리가 적으며 최소의 자원으로 최대의 효율을 내는 것이 좋은 알고리즘이라고 생각합니다.

# 정확도가 동일하다면 그 다음으로 고려해야 될 조건이 뭘까요?

> 알고리즘의 시간복잡도와 공간복잡도를 고려해야합니다.

## 시간복잡도(Time Complexity)

> 알고리즘이 문제를 해결하는데 걸리는 시간을 의미합니다. 보통 Big-O 표기법을 사용합니다.
> 시간 복잡도는 1초,1분 이런 실제시간으로 평가하는게 아닌 문제를 해결하기위한 절차(step)로 평가합니다.

## 공간복잡도(Space Complexity)

> 얼마나 많은 공간(메모리)를 차지하느냐를 분석하는 방법입니다.

## Big-O

> 최악의 경우에 대한 상한을 의미합니다.

- `O(1) (Constant)`
  - 입력 데이터의 크기에 상관없이 일정한 시간이 걸리는 알고리즘을 나타냅니다.
  - 데이터가 얼마나 증가하던 성능에 영향을 미치지 않습니다.

```js
const myArr = [0, 1, 2, 3];
console.log(myArr[0]); // O(1);
console.log(myArr[1]); // O(1);
```

- `O(n) (Linear)`
  - 입력 데이터의 크기에 비래해 처리 시간이 증가하는 알고리즘입니다.

```js
const myArr = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
for (let i = 0; i <= myArr.length; i++) {
  console.log(myArr[i]); // O(n)
}
```

- `O(n²) (quadratic)`
  - 데이터가 많아질수록 처리시간이 급수적으로 많아지는 알고리즘입니다.

```js
for (let i = 0; i <= myArr.length; i++) {
  for (let j = 0; j <= i; j++) {
    console.log(myArr[j]); // O(n²)
  }
}
```

- `O(log N) (Logarithmic)`
  - 연산이 한 번 실행될 때 마다 데이터의 크기가 절반 감소하는 알고리즘입니다. (log의 지수는 항상 2)
  - 이진검색(binary Search)이 대표적입니다.
