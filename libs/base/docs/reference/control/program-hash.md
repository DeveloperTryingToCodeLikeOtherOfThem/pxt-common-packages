# control.programHash

Get a numeric hash that identifies the current compiled program image.

```sig
control.programHash(): number
```

## What this value is for

`programHash()` is a runtime identifier for the *specific* program currently running on the device/simulator.  
If the user changes the program and recompiles, this hash usually changes too.

Common uses:

* scoping per-program data (for example settings namespaces),
* identifying a build in logs/diagnostics,
* separating behavior between different deployed program images.

## `programHash` vs `templateHash`

These two hashes are related but different:

* **`programHash()`**: hash of the current program image (user code + generated artifacts).
* **`templateHash()`**: hash used by the runtime/partial-flashing template pipeline to validate binary compatibility.

In other words, `programHash()` identifies *which program* is running, while `templateHash()` helps check whether an incremental/partial update can be safely applied to a specific runtime template.

## Notes

* `programHash()` is exposed as `control.programHash()` in TypeScript.
* `templateHash()` is a runtime-level API and is not exposed as a regular `control.*` TypeScript function in this package.
