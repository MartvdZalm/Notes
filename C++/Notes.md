# C++

## Function Parameter Passing - std::string
Passes by const reference -> no copy, read-only
```
void open(const std::string& filename)
```
Passes a pointer to a const string. Can be useful when dealing with raw pointers or nullable values (nullptr).
Requires *filename to access data, caller must pass a valid pointer.
```
std::string name = "file.txt";
open(&name);

void open(const std::string* filename)
```
Passes by value -> makes a copy of the string. Can be useful if you need to modify locally without affecting the original,
but less efficient.
```
void open(std::string filename)
```

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
