PHP 8.1, released on **November 25, 2021**, introduced several **new features, performance improvements, and syntax enhancements**. Below are the **most important new features** with examples:

---

## 🔶 1. **Enums (Enumerations)**

Enums allow you to define a custom data type with a fixed set of possible values.

### ✅ Example:

```php
enum Status {
    case Pending;
    case Approved;
    case Rejected;
}

function checkStatus(Status $status) {
    echo "Status: " . $status->name;
}

checkStatus(Status::Approved);  // Output: Status: Approved
```

---

## 🔶 2. **Readonly Properties**

Once a readonly property is initialized, it cannot be changed.

### ✅ Example:

```php
class User {
    public readonly string $name;

    public function __construct(string $name) {
        $this->name = $name;
    }
}

$user = new User("John");
// $user->name = "Doe"; // ❌ Error: Cannot modify readonly property
echo $user->name;  // Output: John
```

---

## 🔶 3. **Fibers** (Lightweight Threads)

Fibers allow better handling of asynchronous and concurrent operations (used heavily in frameworks and libraries).

### ✅ Example:

```php
$fiber = new Fiber(function (): void {
    $value = Fiber::suspend('pause');
    echo "Resumed with value: $value\n";
});

echo $fiber->start(); // Output: pause
$fiber->resume('continue'); // Output: Resumed with value: continue
```

---

## 🔶 4. **Array Unpacking with String Keys**

PHP 8.1 allows unpacking arrays with string keys using the spread operator (`...`), but only for arrays without conflicting keys.

### ✅ Example:

```php
$arr1 = ["a" => 1];
$arr2 = ["b" => 2];
$merged = [...$arr1, ...$arr2];

print_r($merged); 
// Output:
// Array
// (
//     [a] => 1
//     [b] => 2
// )
```

---

## 🔶 5. **`never` Return Type**

Functions declared with `never` must **not return** — they either `exit()`, throw an exception, or cause a fatal error.

### ✅ Example:

```php
function redirect(): never {
    header("Location: /");
    exit;
}
```

---

## 🔶 6. **`final` Constants**

You can declare class constants as `final`, preventing them from being overridden in child classes.

### ✅ Example:

```php
class A {
    final public const VERSION = "1.0";
}

class B extends A {
    // public const VERSION = "2.0"; // ❌ Error
}
```

---

## 🔶 7. **`new` in Initializers**

You can now use `new` inside default parameter values, attributes, etc.

### ✅ Example:

```php
class Logger {
    public function log(string $msg) {
        echo $msg;
    }
}

class Service {
    public function __construct(private Logger $logger = new Logger()) {}

    public function run() {
        $this->logger->log("Running...");
    }
}

$service = new Service();
$service->run(); // Output: Running...
```

---

## 🔶 8. **Performance Improvements**

PHP 8.1 also brings **JIT improvements**, faster class handling, and reduced memory usage.

---

