PHP 8.2 introduced several **new features, improvements, and deprecations** aimed at making the language more secure, performant, and developer-friendly. Below is a summary of the most important updates, along with examples:

---

## ✅ **1. Readonly Classes**

Now you can declare an entire class as `readonly`, meaning **all its properties are readonly**.

### 🔸 Before (PHP 8.1):

```php
class User {
    public readonly string $name;
}
```

### 🔸 Now in PHP 8.2:

```php
readonly class User {
    public string $name;
}

$user = new User();
$user->name = 'Dheeraj'; // ✅ Allowed during initialization
$user->name = 'Kumar';   // ❌ Error: Cannot modify readonly property
```

---

## ✅ **2. Disjunctive Normal Form (DNF) Types**

PHP 8.2 supports **DNF types**, which allow you to combine union (`|`) and intersection (`&`) types in a specific normalized way.

```php
function process((A&B)|C $input) {
    // Valid input: either (A and B) or C
}
```

---

## ✅ **3. `null`, `false`, and `true` as Standalone Types**

PHP 8.2 allows using `null`, `false`, and `true` as independent types.

```php
function alwaysFails(): false {
    return false;
}

function getValue(): null {
    return null;
}
```

---

## ✅ **4. Deprecated Dynamic Properties**

Creating dynamic properties is deprecated. This helps catch bugs due to mistyped property names.

```php
class Product {
    public string $name;
}

$product = new Product();
$product->price = 100; // ❌ Deprecated: Cannot add dynamic property
```

### ✅ Fix: Use `#[AllowDynamicProperties]` or define the property

---

## ✅ **5. New `Random\Randomizer` API**

Improved randomness with `Random\Randomizer` class from the new `Random` extension.

```php
$rnd = new \Random\Randomizer();
echo $rnd->getInt(1, 100); // Secure random number between 1 and 100
```

---

## ✅ **6. `true` Type and `never` Return Type**

PHP 8.2 now allows `true` as a return type and also supports `never` for functions that never return.

```php
function isEnabled(): true {
    return true;
}

function redirect(string $url): never {
    header("Location: $url");
    exit(); // Required
}
```

---

## ✅ **7. Fetching `const` in Traits**

You can now access class constants inside traits using `self::CONST_NAME`.

```php
trait Logger {
    public function log() {
        echo self::LEVEL;
    }
}

class App {
    use Logger;
    public const LEVEL = 'info';
}
```

---

## ✅ **8. `#[SensitiveParameter]` Attribute**

Used to hide sensitive data in stack traces or logs.

```php
function login(#[\SensitiveParameter] string $password) {
    throw new Exception("Failed login");
}

login("secret123"); // Stack trace will hide the actual password
```

---

## ⚠️ **Deprecated Features in PHP 8.2**

* Dynamic properties (without `#[AllowDynamicProperties]`)
* `mbstring` functions with encoding `"pass"`
* Partially supported callables like `$obj::method`
* Using `${}` string interpolation without curly braces

---
