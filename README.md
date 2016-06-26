# mktemp

[Documentation](https://samgiles.github.io/rs-mktemp/mktemp/struct.Temp.html "mktemp docs")

This module provides a simple way of creating temporary files and
directories where their lifetime is defined by the scope they exist in.

Once the variable goes out of scope, the underlying file system resource is removed.

# Example

```
use mktemp::Temp;

{
  let temp_file = Temp::new_file().unwrap();
  let file = try!(fs::File::open(temp_file));
}
// temp_file is cleaned from the fs here
```

# License

MPL v2
