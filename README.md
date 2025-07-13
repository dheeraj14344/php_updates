Here is a list of **important PHP interview questions and answers** tailored for candidates with **2–4 years of experience**. These questions cover **core concepts, OOP, error handling, security, and new features**.

---

## 🧠 **Core PHP Questions**

### 1. **What is the difference between `==` and `===` in PHP?**

* `==` checks **value equality**, with type juggling.
* `===` checks **value and type**.

```php
'5' == 5     // true
'5' === 5    // false
```

---

### 2. **What are the data types in PHP?**

* Scalar: `int`, `float`, `string`, `bool`
* Compound: `array`, `object`, `callable`, `iterable`
* Special: `null`, `resource`

---

### 3. **What is the difference between `include` and `require`?**

* `include`: Warning if file not found; script continues.
* `require`: Fatal error if file not found; script stops.

---

### 4. **What is the difference between `GET` and `POST`?**

* `GET`: Appends data to the URL, limited in size.
* `POST`: Sends data in the body, more secure for sensitive info.

---

### 5. **How to handle errors in PHP?**

* Use `try...catch` for exceptions.

```php
try {
    throw new Exception("Error occurred");
} catch (Exception $e) {
    echo $e->getMessage();
}
```

---

## 🧱 **Object-Oriented PHP**

### 6. **What are the visibility types of class members in PHP?**

* `public`: Accessible everywhere
* `protected`: Accessible in class and subclasses
* `private`: Accessible only in the same class

---

### 7. **What is the use of `final` keyword?**

* `final class`: Cannot be extended.
* `final method`: Cannot be overridden.

---

### 8. **What is the difference between `abstract` class and `interface`?**

| Feature  | Abstract Class     | Interface               |
| -------- | ------------------ | ----------------------- |
| Methods  | Can have body      | Cannot (before PHP 8.0) |
| Multiple | One abstract class | Multiple interfaces     |

---

### 9. **What is the difference between `static` and non-static methods?**

* `static`: Called using `Class::method()`, without `$this`.

---

### 10. **What is a trait in PHP?**

* A way to reuse code across classes (like mixins).

```php
trait Logger {
    public function log($msg) {
        echo $msg;
    }
}

class App {
    use Logger;
}
```

---

## 🧪 **Advanced / Practical Questions**

### 11. **How to connect MySQL with PDO?**

```php
$pdo = new PDO("mysql:host=localhost;dbname=test", "user", "pass");
```

---

### 12. **How to prevent SQL injection in PHP?**

* Use **prepared statements** with PDO or MySQLi.

```php
$stmt = $pdo->prepare("SELECT * FROM users WHERE email = ?");
$stmt->execute([$email]);
```

---

### 13. **What are magic methods in PHP?**

* Special methods like:

  * `__construct()` – Constructor
  * `__destruct()` – Destructor
  * `__get()` / `__set()` – Property overloading
  * `__call()` – Method overloading

---

### 14. **What is session and how is it used?**

```php
session_start();
$_SESSION['user'] = 'admin';
```

Stores user data across requests on the server.

---

### 15. **What is Composer in PHP?**

* Dependency management tool. Uses `composer.json`.

```bash
composer install
composer require vendor/package
```

---

### 16. **Difference between `isset()`, `empty()`, and `is_null()`?**

* `isset($var)` → True if set and not null
* `empty($var)` → True if empty (0, '', false, etc.)
* `is_null($var)` → True if null

---

## ⚙️ **PHP 7/8/8.1/8.2/8.3 Feature Highlights**

### 17. **What are union types in PHP 8.0?**

```php
function test(int|string $value) {}
```

---

### 18. **What is match expression (PHP 8)?**

```php
$role = match($id) {
  1 => 'Admin',
  2 => 'User',
  default => 'Guest'
};
```

---

### 19. **What are named arguments (PHP 8)?**

```php
function greet($name, $time = "morning") {}
greet(name: "Dheeraj", time: "evening");
```

---

### 20. **What is the `readonly` class (PHP 8.2)?**

```php
readonly class Config {
    public string $appName;
}
```

---

## ✅ Bonus Tips

* Always mention **real project experience** using Laravel, API, Composer, MySQL, or frameworks.
* Prepare to explain **MVC architecture**, REST API, middleware, and Eloquent ORM.

---

