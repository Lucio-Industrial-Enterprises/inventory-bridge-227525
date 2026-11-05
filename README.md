# Warehouse tools

Small Python utilities for warehouse order and shipping workflows.

Run the tests with `python3 -m unittest discover -s tests -v`.

## Shipping

`shipping_quote(weight_kg, zone, service="standard")` returns a shipping quote
in dollars. Zones are `local` and `regional`; weights must be positive.
The `service` parameter accepts `"standard"` (default) or `"express"`.
Express shipping costs $7.00 more than the equivalent standard quote.
An unknown zone or service raises `ValueError`.

### CLI

```
python -m warehouse.cli <weight_kg> <zone> [--service {standard,express}]
```

Examples:

```
python -m warehouse.cli 2 local                   # standard: $8.00
python -m warehouse.cli 2 local --service express # express:  $15.00
```
