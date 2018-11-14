
## Cargo

### Useful additional commands

* **cargo install cargo-check** (The command allows you to check the code, without build)
* **cargo install cargo-edit** (The command allows you to manage dependencies[add, rm, list].)
* **cargo install cargo-graph** (The command generates a dependency graph in GraphViz format.)
 *cargo graph > deps.dot && cargo graph > deps.dot && dot deps.dot -Tpng -o deps.png*
* **cargo install cargo-watch** (The command allows you to automatically collect code when changes are made to files.)
* **cargo install cargo-count** (The command allows you to calculate useful statistics about your code.)
*  **cargo install rustfmt** (The command allows you to automatically format the code.)


## Source code

### How to return &str from a function?

use &'static str:

```rust
fn find_number(val: i32) -> &'static str {
    match val {
        7 => "seven",
        8 => "eight",
        _ => unreachable!(),
    }
}
```
### How to print stack trace?
```rust
use std::fs::File;  
n main()  
{  
   let f = File::open("vector.txt");  
   match f   
   {  
       Ok(file) => file,  
       Err(error) => {  
       panic!("There was a problem opening the file: {:?}", error)  
     },  
   };
 ```  
 
 ### How do I print the type of a variable?
 
 ```rust
#![feature(core_intrinsics)]

fn print_type_of<T>(_: &T) {
    println!("{}", unsafe { std::intrinsics::type_name::<T>() });
}

fn main() {
    print_type_of(&32.90);          // prints "f64"
    print_type_of(&vec![1, 2, 4]);  // prints "std::vec::Vec<i32>"
    print_type_of(&"foo");          // prints "&str"
}
 ```
