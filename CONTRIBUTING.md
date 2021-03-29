If you want to contribute to any of this organisation's project, read this file before.
# Definitions
UDI - User Defined Identifier (variable, constant, constexpr, function, type, procedure, static-initialised identifiers, etc.)
translator - preproccessor, transpiler, compiler, interpreter, VM
# Future plans
C++Script is expected to have built-in reflection (by holding information about UDIs within translators) and to be DSL-oriented but still as GPL. It is maintained with the spirit of scripting.

# Coding conventions
Whole C++Script standard library should be in `std` namespace and whole C++ standard library should be in `cpp.std` namespace.
Example:
```cpp
ns cpp
begin
    ns std
    begin
        template<typename _Ty, typename _Alloc=allocator<_Ty>>
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
In C++ STL, coding conventions are the same as in original C++ STL.
- curly braces (`{}`) in functions or types or loops or ifs are at new line

In C++S part of stdlib and in translators convention is:
- variables are `snake_case`, except short names (e.g. `plusop`)
- constants are `PascalCase` even if it is one letter (except math or physics or chemical constants like `pi`, `e`, `phi`, `g`, `Me`)
- functions are `PascalCase`, except short name like run or help or compile or version or build
- types are `camelCase`, but if it is one word, then `PascalCase`, if it is one letter, then it is small letter
- macros are `UPPERCASE`, except syntactic extensions, like `endfor` or `until()`
- indentation has 4 spaces
- `begin` is at new line, but `do` and `then` are at the same line
Example:
```cpp
ns example
begin
    procedure Example(int& x)
    begin
        if x == 10 then
            until x == 0 do
                x--
            end
        endif
    end
end
```
- Use `this` in types instead of `m_` or `_var` or `var_`.