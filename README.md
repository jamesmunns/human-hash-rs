# Human Hash (Rust)

human hash provides human-readable representations of digests.

This is a Rustlang port of [Zachary Voase's humanhash](https://github.com/zacharyvoase/humanhash) for Python.

## Usage

Use this library to generate human readable and reproducible hash summaries. Useful when looking at a list of UUIDs, or as a shorthand way to remember and select from hard to remember list.

Don't use this for security purposes.

## Example

```rust
extern crate human_hash;
extern crate uuid;

use human_hash::humanize;
use uuid::Uuid;

fn main() {
    let my_uuid = Uuid::parse_str("7528880a986c40e78c38115e640da2a1").unwrap();
    let my_digest = humanize(&my_uuid, 4);

    println!("Original Hash: {}", my_uuid);
    println!("Digest:        {}", my_digest);
}
```

### Output
```bash
➜  humanize_demo git:(master) ✗ cargo run
   Compiling humanize_demo v0.1.0
    Finished debug [unoptimized + debuginfo] target(s) in 0.45 secs
     Running `target/debug/humanize_demo`

Original Hash: 7528880a-986c-40e7-8c38-115e640da2a1
Digest:        three-georgia-xray-jig
```

## License
Licensed under the MIT license
