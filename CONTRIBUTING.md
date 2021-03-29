If you want to contribute to any of this organisation's project, read this file before.
# Definitions
UDI - User Defined Identifier (variable, constant, constexpr, function, type, procedure, static-initialised identifiers, etc.)
translator - preproccessor, transpiler, compiler, interpreter, VM
# Future plans
C++Script is expected to have built-in reflection (by holding information about UDIs within translators) and to be DSL-oriented but still as GPL. It is maintained with the spirit of scripting.

# Coding conventions
Whole C++Script standard library should be in std namespace and whole C++ standard library should be in cpp.std namespace.
Example:
```cpp
ns cpp
begin
    ns std
    begin
        template<typename T, typename Alloc=cpp.std.allocator<T>>
        class vector
        begin
        ...
        end
    end
end
ns std
begin
    template<typename T, typename Alloc=cpp.std.allocator<T>>
    class Vector inherit Container<T, Alloc>
    begin
    ...
    end
end
```
