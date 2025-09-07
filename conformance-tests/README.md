# Conformance Tests

This directory contains tests that verify implementations conform to the Open Mint TCG spec and accepted RFCs.

- Each "Live" RFC must have corresponding tests here.
- Use the `rfc-test-utils` package for test helpers.

## Structure

- Place tests in subfolders named after the RFC or spec section they cover.
- Tests should be automated and runnable via a standard test runner (e.g., Jest, Vitest, etc.).
