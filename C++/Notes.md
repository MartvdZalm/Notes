# C++

## Memory Management: Stack vs Heap
### Stack Allocation (automatic)
- Object is destroyed automatically when it goes out of scope.
- No **new** / **delete** needed.
```
Person person;
```

### Heap Allocation (manual)
- Use **new** to allocate, must use **delete** to free memory.
- Needed for dynamic lifetime or polymorphism
```
Person* person = new Person(); // Lives on the heap
delete person;                 // Must clean up manually
```

### Smart Pointers (modern C++)
https://cplusplus.com/reference/memory/unique_ptr/
- Manages heap memory automatically.
- Prefer **std::unique_ptr** or **std::shared_ptr**.
```
std::unique_ptr<Person> person = std::make_unique<Person>();
```

### Quick Rule
- Prefer stack when possible.
- Use heap only when you need dynamic lifetime or polymorphism.
- Use smart pointers instead of raw **new** / **delete**.


## char[] to std::string
```
#include <iostream>
#include <string>

int main()
{
    char name[] = "John Doe";
    std::string strName(name);
    
    std::cout << "std::string: " << strName << std::endl;
}
```
