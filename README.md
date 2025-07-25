# std_derive
Implements the `derive`-macro and the basic `derive_*`-macros.

### Usage Example

```
// Writing the following before a type declaration ('struct' or 'enum')...
@derive(eq, clone, as_hash, as_string)
pub struct Cat(name: String, age: Int)

// ...will generate:

// from 'eq':
pub fun Cat::eq(lhs: Cat, rhs: Cat) -> Bool
pub fun Cat::not_eq(lhs: Cat, rhs: Cat) -> Bool

// from 'clone':
pub fun Cat::clone(self: Cat) -> mut Cat

// from 'as_hash':
pub fun Cat::as_hash(self: Cat) -> Int

// from 'as_string':
pub fun Cat::as_string(self: Cat) -> String

// Each of these functions require that that function is also implemented for each of the member types.
```