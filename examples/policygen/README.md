# Example Policy Generator configs

This directory contains example Policy Generator configs.

The [generated/](./generated) directory contains policies generated by the
Policy Generator using the example config.

To regenerate the policies, run the following commands:

```bash
# To be run at the git repository root.
go install ./cmd/policygen
policygen --config_path=examples/policygen/config.hcl \
  --state_paths=examples/policygen/example.tfstate \
  --output_path=examples/policygen/generated
```
