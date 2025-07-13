PHP 7.4, released on **November 28, 2019**, introduced several new features and optimizations to improve performance, code readability, and maintainability. Below are the **key features** with **examples**:

---

### ✅ 1. **Arrow Functions (Short Closures)**

Arrow functions provide a more concise syntax for anonymous functions and automatically capture variables from the parent scope.

**Before (Anonymous function):**

```php
$numbers = [1, 2, 3];
$squares = array_map(function($n) {
    return $n * $n;
}, $numbers);
```

**After (Arrow function):**

```php
$numbers = [1, 2, 3];
$squares = array_map(fn($n) => $n * $n, $numbers);
```

---

### ✅ 2. **Typed Properties**

You can now declare types for class properties (e.g., `int`, `string`, `array`, `object`, etc.)

```php
class User {
    public int $id;
    public string $name;
}

$user = new User();
$user->id = 1;
$user->name = "Dheeraj";
```

---

### ✅ 3. **Null Coalescing Assignment Operator (`??=`)**

This is shorthand for `if not set, then assign`.

**Before:**

```php
$data['user'] = $data['user'] ?? 'guest';
```

**After:**

```php
$data['user'] ??= 'guest';
```

---

### ✅ 4. **Spread Operator in Arrays**

Allows unpacking arrays into another array.

```php
$array1 = [1, 2, 3];
$array2 = [4, 5, ...$array1];

print_r($array2); // [4, 5, 1, 2, 3]
```

---

### ✅ 5. **Preloading**

Improves performance by loading classes and functions into memory before any code runs (requires server config like in `opcache.preload` in `php.ini`).

```php
// preload.php
require_once "MyClass.php";
require_once "functions.php";
```

Configure in `php.ini`:

```ini
opcache.preload=/path/to/preload.php
```

---

### ✅ 6. **Deprecations (For Future Compatibility)**

PHP 7.4 deprecated some old functionalities to prepare for PHP 8. Examples:

* **Curly brace array/string access**:

  ```php
  $str = "abc";
  echo $str{1}; // Deprecated in 7.4
  echo $str[1]; // Use this instead
  ```

* **Real type is deprecated**

  ```php
  function calc(real $a) {} // Deprecated
  ```

---

### ✅ 7. **Weak References**

Allow referencing an object without preventing it from being garbage-collected.

```php
$obj = new stdClass();
$weakRef = WeakReference::create($obj);

var_dump($weakRef->get()); // object(stdClass)

unset($obj);

var_dump($weakRef->get()); // NULL
```

---

### ✅ 8. **Covariant and Contravariant Types**

Supports more precise type declarations in class inheritance.

* **Covariant Return Types** – allows child method to return a more specific type.
* **Contravariant Parameter Types** – allows child method to accept a more general type.

```php
class Animal {}
class Dog extends Animal {}

class AnimalShelter {
    function getAnimal(): Animal {}
}

class DogShelter extends AnimalShelter {
    function getAnimal(): Dog {} // Covariant return
}
```

---

### ✅ 9. **FFI (Foreign Function Interface)**

Allows calling C functions directly from PHP.

```php
$ffi = FFI::cdef(
    "int abs(int x);",
    "libc.so.6"
);

echo $ffi->abs(-10); // Outputs: 10
```

---

### ✅ 10. **Improved Performance**

* PHP 7.4 offers **10–20% speed improvements** compared to PHP 7.3.
* Reduced memory usage.

---

### 🧠 Summary

| Feature                       | Description                    |
| ----------------------------- | ------------------------------ |
| Arrow Functions               | Short syntax for closures      |
| Typed Properties              | Type-safe class properties     |
| Null Coalescing Assignment    | Shorthand assignment           |
| Spread Operator in Arrays     | Merge/unpack arrays easily     |
| Preloading                    | Boost performance              |
| Weak References               | Non-blocking object references |
| Covariant/Contravariant Types | Better OOP support             |
| FFI                           | Call C functions in PHP        |
| Deprecations                  | Cleaner syntax going forward   |

---

Great! Here are **real-world examples and exercises** for key PHP 7.4 features to help solidify your understanding:

---

## 🧩 1. **Arrow Functions – Example**

### ✅ Use Case: Calculate discounted prices

```php
$prices = [100, 200, 300];
$discounted = array_map(fn($price) => $price * 0.9, $prices);

print_r($discounted); // [90, 180, 270]
```

---

## 📝 Exercise:

Use an arrow function to convert an array of Celsius temperatures to Fahrenheit.

```php
$celsius = [0, 20, 30];
// Your code here
```

---

## 🧩 2. **Typed Properties – Example**

### ✅ Use Case: Enforce type safety

```php
class Product {
    public int $id;
    public string $name;
    public float $price;
}

$product = new Product();
$product->id = 1;
$product->name = "Mouse";
$product->price = 799.99;

echo "{$product->name} costs ₹{$product->price}";
```

---

## 📝 Exercise:

Create a `User` class with typed properties for `id` (int), `name` (string), and `email` (string).

---

## 🧩 3. **Null Coalescing Assignment – Example**

### ✅ Use Case: Set defaults

```php
$user = [];

$user['role'] ??= 'guest';

echo $user['role']; // guest
```

---

## 📝 Exercise:

Set a default `'status'` of `'inactive'` in an array if it’s not already set.

```php
$data = ['name' => 'Dheeraj'];
// Your code here
```

---

## 🧩 4. **Spread Operator in Arrays – Example**

### ✅ Use Case: Merging arrays

```php
$defaults = ['host' => 'localhost', 'port' => 3306];
$custom = ['port' => 5432];

$config = [...$defaults, ...$custom];

print_r($config);
// ['host' => 'localhost', 'port' => 5432]
```

---

## 📝 Exercise:

Combine multiple arrays of student names using the spread operator.

```php
$a = ['John', 'Amit'];
$b = ['Sara'];
$c = ['Meena'];
// Your code here
```

---

## 🧩 5. **Weak References – Example**

### ✅ Use Case: Cache without blocking GC

```php
class FileCache {}
$obj = new FileCache();
$weak = WeakReference::create($obj);

unset($obj);

var_dump($weak->get()); // NULL (object collected)
```

---

## 📝 Exercise:

Create a weak reference to any object and check if it is available before and after `unset()`.

---

## 🧩 6. **Preloading – Example** *(Advanced)*

Preloading is configured in `php.ini` and not used directly in code:

```ini
opcache.preload=/var/www/html/preload.php
```

**`preload.php` Example:**

```php
require_once "classes/User.php";
require_once "helpers/functions.php";
```

🧠 *This loads files into memory before requests, boosting performance in large apps.*

---

## 🧩 7. **Covariant Return Types – Example**

```php
class Animal {}
class Dog extends Animal {}

class Shelter {
    public function getAnimal(): Animal {
        return new Animal();
    }
}

class DogShelter extends Shelter {
    public function getAnimal(): Dog {
        return new Dog(); // More specific return type
    }
}
```

---

## ✅ Summary of Exercises

| Feature          | Task Description                          |
| ---------------- | ----------------------------------------- |
| Arrow Function   | Convert Celsius to Fahrenheit             |
| Typed Properties | Create User class with typed fields       |
| Null Coalescing  | Set default array value                   |
| Spread Operator  | Merge 3 arrays into one                   |
| Weak References  | Observe object GC behavior                |
| Covariant Return | Override method with more specific return |

---


