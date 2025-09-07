# RFC Test Utils

This package provides utilities for writing conformance tests for Open Mint TCG RFCs and the spec.

## Usage

Import helpers from this package in your conformance tests to:
- Assert compliance with RFC requirements
- Share common test logic
- Simplify test setup/teardown

## Example

```js
import { assertRfcCompliant } from 'rfc-test-utils';

test('Example RFC compliance', () => {
  assertRfcCompliant(/* ... */);
});
```

Add more utilities as needed to support testing RFCs and spec features.
