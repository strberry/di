# 🍓 Extension: DI Container
This is a simple di container for [strawberry](https://github.com/elderguardian/strawberry), but you could easily use it in other frameworks.
## Installation
```
mkdir src/foundations && cd src/foundations
git clone https://github.com/strberry/di.git strawberry-di
```
### How to add mappings
Somewhere in your app, create a static kernel variable like this.
This could for example be at the top of your `index.php`.
```php
$kernel = new Kernel([
    IMyInterface::class => Implementation::class,
]);
```

### How to use it
##### **`src/controllers/YourController.php`**
```php
    ...

    public function world() {
        //Get class from interface string
        $implementation = $kernel->get(IMyInterface:class);
        return $this->respond('Hello, world!');
    }

    ...
```
