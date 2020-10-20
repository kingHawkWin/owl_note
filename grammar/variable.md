---
description: 变量/常量 声明
---

# variable

{% tabs %}
{% tab title="JavaScript" %}
```javascript
// start               varFoo = undefined

var varFoo = 1      // 1
// ^ 变量提升
console.log(letFoo) // 运行时报错
let letFoo          // undefined
letFoo = 1          // 1
let letFoo          // 运行时报错
// ^ 声明后赋值
let letBar = 1      // 1
// ^ 声明时赋值
{
  let letBaz = 1    // 1
}
console.log(letBaz) // 运行时报错
// ^ 块内生命周期
const CONSTFOO = 1  // 1
CONSTFOO = 2        // 运行时报错
const CONSTBAR = [] // []
CONSTBAR.push(1)    // [1]

// end
```
{% endtab %}

{% tab title="typescript" %}
```typescript
// start

var varFoo = 1      // 1
// ^ 变量提升
console.log(letFoo) // 编译时报错
let letFoo          // undefined
letFoo = 1          // 1
let letFoo          // 编译时报错
// ^ 声明后赋值
let letBar = 1      // 1
// ^ 声明时赋值
{
  let letBaz = 1    // 1
}
console.log(letBaz) // 编译时报错
// ^ 块内生命周期
const CONSTFOO = 1  // 1
CONSTFOO = 2        // 编译时报错
const CONSTBAR = [] // []
CONSTBAR.push(1)    // [1]

// end
```
{% endtab %}

{% tab title="dart" %}
```dart
//  start

void f() {
  var varFoo;                // null
  dynamic dynamicFoo;        // null
  varFoo = 1;                // 1
  dynamicFoo = 1;            // 1
  varFoo = 'varFoo';         // varFoo
  dynamicFoo = 'dynamicFoo'; // dynamicFoo
  
  int intFoo = 1;            // 1
  intFoo = 'intFoo';         // 编译报错
  
  final finalFoo;            // 编译报错
  const constFoo;            // 编译报错
  final finalBar = 1;        // 1
  const constBar = 1;        // 1
  finalBar = 'finalBar';     // 编译报错
  constBar = 'constBar';     // 编译报错
}

//  end
```
{% endtab %}

{% tab title="go" %}
```go
//  start

var varFoo           // 0

func f() {
  varFoo = 1         // 1
  varBar := 1        // 1
  var varBaz int = 1 // 1
  
  const constUntypedFoo = 1                                   // 1
  const constUntypedBar = constUntypedFoo * 2.3               // 2.3
  const constTypedFoo int = 4                                 // 4
  const constTypedBar float64 = 3.5                           // 3.5
  const constTypedBaz float64 = constTypedBar / constTypedFoo // 编译报错
  const constTypedBaz float64 = constTypedBar / 4             // 0.875
}

//  end
```
{% endtab %}

{% tab title="rust" %}
```rust
//  start

fn main() {
  let let_foo = 1;             // 1
  let_foo = 2;                 // 编译报错
  let let_foo = "2";           // "2"
  
  let mut let_bar = 3;         // 3
  letBar = "4";                // 编译报错
  letBar = 4;                  // 4
  
  let let_baz = 5;
  let let_baz = let_baz * 8;
  let let_baz = let_baz / 7.5; // 编译报错
  let let_baz = let_baz / 7;   // 5
  
  let mut let_never_used = 1;  // 编译报错
  
  const PI: f64 = 3.141592653  // 3.141592653
}

//  end
```
{% endtab %}
{% endtabs %}

