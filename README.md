# Example Testing Package README

## Project Structure

* **build-scripts/** – Scripts used to compile/build the testing package (e.g., generating JS).
* **example_escrow/** – Example program showcasing how a developer can use the testing package helpers to write integration tests.
* **testing/** – The core testing package — contains fixtures, matchers, helpers, log inspectors, etc.

```
example_testing_package/
├─ build-scripts/
├─ example_escrow/
│  ├─ tests/
│  │  └─ escrow_program1.ts
├─ testing/
│  ├─ __tests__/
│  ├─ fixtures/
│  ├─ helpers/
│  ├─ matchers/
│  └─ txLogInspector/
└─ .gitignore
```

## How to Build the Testing Package

```bash
cd testing
pnpm run compile:js
```

This compiles the TypeScript source of the testing helpers into JavaScript.

## How to Run the Example

### ✅ Method 1 — Direct Script Execution

```bash
cd example_escrow
pnpm tsx tests/escrow_program1.ts
```

### ✅ Method 2 — Using Anchor (if modifying Anchor program)

```bash
anchor test --skip-deploy --skip-local-validator
```

Only needed when you modify the Anchor smart contract itself — this skips the local validator startup and deployment.

## Summary

* `build-scripts` → internal build utilities
* `testing` → actual helper framework
* `example_escrow` → real usage demo for developers

This setup allows rapid local Anchor testing with reusable utilities.
