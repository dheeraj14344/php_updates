As of now (July 2025), **PHP 8.4** is still in development and is expected to be released in **November 2025**. However, the PHP team has already proposed and implemented several new features and changes in the **RFCs (Request for Comments)**.

Here’s a summary of the **confirmed or expected features** in PHP 8.4 (based on RFCs accepted or likely to be accepted), along with examples:

---

## ✅ 1. **Array Sorting with Custom Comparison Callbacks**

**Feature:** New functions like `array_sort`, `array_sort_keys`, and `array_sort_values` allow **sorting with a callback**.

### 🔹 Example:

```php
$array = ['apple' => 2, 'banana' => 1, 'cherry' => 3];

$result = array_sort($array, fn($a, $b) => $b <=> $a);
print_r($result);
```

**Output:**

```php
Array
(
    [cherry] => 3
    [apple] => 2
    [banana] => 1
)
```

---

## ✅ 2. **Fetch Properties of Enums in Const Expressions**

**Feature:** You can now use **enum properties** in constant expressions like `class constants` or `attribute arguments`.

### 🔹 Example:

```php
enum Status: string {
    case ACTIVE = 'active';
    case INACTIVE = 'inactive';
}

class User {
    public const DEFAULT_STATUS = Status::ACTIVE->value;
}
```

---

## ✅ 3. **Typed Class Constants**

**Feature:** You can now specify types for **class constants**, improving static analysis and type safety.

### 🔹 Example:

```php
class Config {
    public const string APP_NAME = 'MyApp';
    public const int VERSION = 2;
}
```

---

## ✅ 4. **New `#[\Override]` Attribute**

**Feature:** A new `#[\Override]` attribute ensures that the method **overrides** a method from a parent class or interface. If it doesn’t, PHP will throw an error.

### 🔹 Example:

```php
class Base {
    public function run(): void {}
}

class Child extends Base {
    #[\Override]
    public function run(): void {}
}
```

🧱 If `run()` doesn't exist in the parent, PHP will throw an error.

---

## ✅ 5. **Improved `Closure` Performance**

**Feature:** Internal optimization for closures and anonymous functions – not visible in syntax, but improves runtime performance.

---

## ✅ 6. **Better `Date/Time` Exceptions**

**Feature:** Creating an invalid `DateTimeImmutable` will now throw an **exception by default**, rather than silently failing.

```php
$date = new DateTimeImmutable('invalid-date');
// PHP 8.4 throws a warning or exception
```

---

## ✅ 7. **More Accurate `get_debug_type()`**

**Feature:** Improved detection and naming for types like enums and anonymous classes.

---

## ✅ 8. **Readonly Class Improvements**

* **Readonly class properties** are more efficient.
* You may see further syntax support or fixes related to readonly classes.

---

## ✅ 9. **More Strict Type Enforcement**

PHP continues moving toward **stricter typing**, so deprecated flexible behaviors will throw more warnings or errors.

---

## ✨ Bonus: Possible Upcoming Features (Not Yet Finalized)

* `array_column` enhancement to support object properties.
* New syntax for method call chaining on null (like safe navigation).
* New standard library functions.

---

## 🗓 Release Timeline

| Milestone              | Date              |
| ---------------------- | ----------------- |
| Alpha Releases         | June–July 2025    |
| Beta Releases          | August 2025       |
| RC (Release Candidate) | Sept–Oct 2025     |
| 📦 Final Release       | **November 2025** |

---

## 📚 Summary Table

| Feature                            | Type | PHP 8.4 |
| ---------------------------------- | ---- | ------- |
| `array_sort()` with callback       | ✔️   | ✅       |
| Enum properties in const           | ✔️   | ✅       |
| Typed class constants              | ✔️   | ✅       |
| `#[\Override]` attribute           | ✔️   | ✅       |
| Better DateTime exception handling | ✔️   | ✅       |
| Closure performance improvements   | ⚙️   | ✅       |
| Stricter typing                    | 🚧   | ✅       |

---

