# Template hash (`templateHash`)

`templateHash` is a low-level runtime hash used for binary/template compatibility checks.

It is primarily used by the runtime when validating whether a partially flashed or incrementally updated image matches the expected runtime template.

## How it differs from program hash

* **`templateHash`**: compatibility hash for the runtime/template layout.
* **`programHash`**: identity hash for the currently compiled program.

If you are writing app-level logic, prefer `control.programHash()` for identifying the current program.
