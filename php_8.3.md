PHP 8.3, released on **November 23, 2023**, introduced several new features, improvements, and deprecations to enhance performance, developer experience, and type safety.

---

## ✅ **New Features in PHP 8.3 with Examples**

---

### 1. **Readonly Classes**

You can declare an entire class as `readonly` instead of marking each property.

**✅ Example:**

```php
readonly class User {
    public function __construct(
        public string $name,
        public int $age
    ) {}
}

$user = new User("John", 30);
echo $user->name; // John
// $user->name = "Doe"; // ❌ Error: Cannot modify readonly property
```

---

### 2. **Dynamic Class Constant Fetch**

Now you can use dynamic expressions to access class constants.

**✅ Example:**

```php
class Status {
    public const ACTIVE = 'active';
    public const INACTIVE = 'inactive';
}

$constName = 'ACTIVE';
echo Status::{$constName}; // active
```

---

### 3. **json\_validate() Function**

Introduced a new function to **validate JSON without decoding**.

**✅ Example:**

```php
$valid = '{"name":"John"}';
$invalid = '{name:"John"}';

var_dump(json_validate($valid));   // true
var_dump(json_validate($invalid)); // false
```

---

### 4. **Improved `Random` Extension**

New `Random\Randomizer` class with pluggable engines (like `Xoshiro256StarStar`).

**✅ Example:**

```php
use Random\Randomizer;
use Random\Engine\Xoshiro256StarStar;

$randomizer = new Randomizer(new Xoshiro256StarStar());
echo $randomizer->getInt(1, 100); // e.g. 56
```

---

### 5. **Explicit Octal Integer Literal**

New prefix `0o` for octal literals (like in other languages).

**✅ Example:**

```php
$octal = 0o77; // Equals 63 in decimal
echo $octal;
```

---

### 6. **Anonymous Readonly Classes**

You can now define anonymous classes as `readonly`.

**✅ Example:**

```php
$readonly = readonly new class(10) {
    public function __construct(public int $value) {}
};

echo $readonly->value; // 10
```

---

### 7. **Type System Improvements**

* **New warning when calling non-static methods statically**

**✅ Example:**

```php
class Test {
    public function hello() {
        return "Hello";
    }
}

echo Test::hello(); // Deprecated warning in PHP 8.3
```

---

## ⚠️ **Deprecations in PHP 8.3**

| Deprecated Feature                            | Replacement / Note   |
| --------------------------------------------- | -------------------- |
| `mktime()` and `gmmktime()` without arguments | Now deprecated       |
| Calling non-static methods statically         | Triggers deprecation |
| Using negative values in `String offset`      | Deprecated           |

---

## 🔧 Performance Improvements

* Continued internal optimization.
* Improved Just-in-Time (JIT) performance in specific scenarios.

---
# Laravel
----
Here’s how some **PHP 8.3 features** can be practically used in a **Laravel** project (like models, services, or config files):

---

## ✅ 1. **Readonly Class in a Laravel DTO**

Use `readonly` classes for **Data Transfer Objects** (DTOs) or value objects.

### 📦 Example: DTO in `App\Data\UserData.php`

```php
namespace App\Data;

readonly class UserData {
    public function __construct(
        public string $name,
        public string $email,
        public int $age,
    ) {}
}
```

### Usage in Controller:

```php
use App\Data\UserData;

public function store(Request $request)
{
    $data = new UserData(
        name: $request->input('name'),
        email: $request->input('email'),
        age: $request->input('age'),
    );

    // Can safely pass to service layer
    UserService::create($data);
}
```

---

## ✅ 2. **json\_validate() for API Input Check**

Useful when you're receiving raw JSON in **webhooks** or external APIs.

### Example in a Controller:

```php
public function webhook(Request $request)
{
    $json = $request->getContent();

    if (!json_validate($json)) {
        return response()->json(['error' => 'Invalid JSON'], 400);
    }

    $data = json_decode($json, true);
    // Proceed with $data
}
```

---

## ✅ 3. **Dynamic Class Constants for Status Handling**

Instead of hardcoding, use dynamic class constant access in Eloquent filters or policies.

### 📦 Example: Status Enum-like Class

```php
namespace App\Enums;

class UserStatus {
    public const ACTIVE = 'active';
    public const INACTIVE = 'inactive';
    public const BANNED = 'banned';
}
```

### Usage:

```php
$status = 'ACTIVE';
$users = User::where('status', UserStatus::{$status})->get();
```

---

## ✅ 4. **Randomizer in Laravel Seeder**

Use the new `Random\Randomizer` in seeders for better randomness control.

### 📦 `database/seeders/UserSeeder.php`

```php
use Random\Randomizer;
use Random\Engine\Xoshiro256StarStar;

public function run()
{
    $randomizer = new Randomizer(new Xoshiro256StarStar());

    User::factory(10)->create([
        'age' => fn () => $randomizer->getInt(18, 65),
    ]);
}
```

---

## ✅ 5. **Anonymous Readonly Class in Config or One-off Use**

Example of quick, immutable config values in boot methods or closures.

```php
$settings = readonly new class() {
    public string $appName = 'MyLaravelApp';
    public int $version = 1;
};

echo $settings->appName;
```

---

## 🔒 Bonus: Better Type Safety and Static Analysis

With readonly and strict features from PHP 8.3, tools like **PHPStan**, **Psalm**, and **Laravel Pint** become more powerful.

---


