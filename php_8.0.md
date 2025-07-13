PHP 8.0, released on **November 26, 2020**, introduced several powerful and long-awaited features. Below are the key features with **examples**:

---

### ✅ 1. **Named Arguments**

Allows passing arguments to a function by parameter name, skipping optional ones.

```php
function greet($name, $greeting = 'Hello') {
    return "$greeting, $name!";
}

// Positional
echo greet("Dheeraj", "Hi");

// Named
echo greet(name: "Dheeraj"); // Uses default greeting: Hello
```

---

### ✅ 2. **Union Types**

Functions can accept multiple types using `|` separator.

```php
function calculateTotal(int|float $price) {
    return $price * 1.18;
}

echo calculateTotal(100);    // 118
echo calculateTotal(99.50);  // 117.41
```

---

### ✅ 3. **Match Expression** (Better than `switch`)

More concise and strict comparisons.

```php
$status = 200;

echo match($status) {
    200 => 'OK',
    404 => 'Not Found',
    500 => 'Server Error',
    default => 'Unknown',
};
```

---

### ✅ 4. **Constructor Property Promotion**

Less boilerplate in class constructors.

```php
class User {
    public function __construct(
        public string $name,
        public int $age
    ) {}
}

$user = new User("Dheeraj", 25);
echo $user->name; // Dheeraj
```

---

### ✅ 5. **Nullsafe Operator `?->`**

Avoids errors when chaining methods/properties on `null`.

```php
class Profile {
    public ?string $bio;
}
class User {
    public ?Profile $profile;
}

$user = new User();
echo $user->profile?->bio; // null, no error!
```

---

### ✅ 6. **JIT (Just-in-Time) Compilation**

Improves performance in some scenarios (mostly CPU-heavy or math operations).

> Not directly visible in code, but JIT improves execution speed in some cases.

---

### ✅ 7. **Attributes (Annotations)**

Native way to add metadata using `#[Attribute]` instead of PHPDoc.

```php
#[Attribute]
class Route {
    public function __construct(public string $path) {}
}

#[Route('/home')]
function homePage() {
    echo "Welcome to Home";
}
```

---

### ✅ 8. **Throw is now an expression**

You can throw exceptions in more flexible ways.

```php
$value = $data['name'] ?? throw new Exception("Name is required");
```

---

### ✅ 9. **Static Return Type**

Can now use `static` as return type for methods returning instance of same class.

```php
class Test {
    public function create(): static {
        return new static();
    }
}
```

---

### ✅ 10. **Weak Maps**

Helps with memory management by allowing garbage collection of unused keys.

```php
$map = new WeakMap();
$obj = new stdClass();

$map[$obj] = "data";

unset($obj); // $obj can now be garbage collected
```

---
Great! Since PHP doesn’t run natively in the browser like JavaScript, we can use an online PHP playground for live testing.

### 🔗 Try PHP 8.0 Features Live Here:

You can use these trusted platforms:

1. **[PHP Online - phpsandbox.io](https://phpsandbox.io)**

   * Direct Link: [https://phpsandbox.io](https://phpsandbox.io)
   * ✅ Supports PHP 8.0+ features
   * 💡 You can save and share code snippets.

2. **[3v4l.org - PHP Version Comparison](https://3v4l.org)**

   * Direct Link: [https://3v4l.org](https://3v4l.org)
   * 📊 Great for testing across multiple PHP versions (including PHP 8.0)

---

### ✅ Sample Snippet to Try (Copy and Paste):

```php
<?php

function greet(string $name, string $greeting = "Hello"): string {
    return "$greeting, $name!";
}

// Named arguments
echo greet(name: "Dheeraj") . PHP_EOL;

// Match expression
$status = 404;
echo match ($status) {
    200 => "OK",
    404 => "Not Found",
    500 => "Server Error",
    default => "Unknown"
} . PHP_EOL;

// Constructor promotion
class User {
    public function __construct(
        public string $name,
        public int $age
    ) {}
}
$user = new User("Dheeraj", 25);
echo "User: $user->name, Age: $user->age\n";

// Nullsafe operator
class Profile {
    public ?string $bio = "PHP Developer";
}
class Person {
    public ?Profile $profile = null;
}
$person = new Person();
echo $person->profile?->bio ?? "No bio found";
```

---

