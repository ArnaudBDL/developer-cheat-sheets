# Python : Testing

## unittest Example

```python
import unittest

class TotalTests(unittest.TestCase):
    def test_empty_values_return_zero(self) -> None:
        self.assertEqual(calculate_total([]), 0)

if __name__ == "__main__":
    unittest.main()
```

## Run

```bash
python -m unittest
python -m unittest discover -s tests
```

Test behavior rather than implementation details. Cover normal, boundary, error and security cases; isolate external systems; use deterministic data; and run tests from a clean environment.
