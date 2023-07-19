# `multicall`
Execute multiple deploy (via UDC) or invoke calls ensuring atomicity.

## `--path, -p <CONTRACT_ADDRESS>`
Required.

Path to a TOML file with call declarations.

File example:

```toml
[[call]]
call_type = "deploy"
class_hash = "0x076e94149fc55e7ad9c5fe3b9af570970ae2cf51205f8452f39753e9497fe849"
inputs = []
id = "map_contract"
unique = false

[[call]]
call_type = "invoke"
contract_address = "0x38b7b9507ccf73d79cb42c2cc4e58cf3af1248f342112879bfdf5aa4f606cc9"
function = "put"
inputs = ["0x123", "234"]

[[call]]
call_type = "invoke"
contract_address = "map_contract"
function = "put"
inputs = ["0x123", "234"]
```