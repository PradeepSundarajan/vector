---
what: "`file` and `files` top-level fields on the `remap` transform"
deprecated_since: "0.58.0"
---

The `file` and `files` top-level configuration fields on the `remap` transform are deprecated.
Use the `source` field with a `type: disk` object instead.

Migrate `file` by replacing:

```yaml
type: remap
file: path/to/program_1.vrl
```

with:

```yaml
type: remap
source:
  type: disk
  files:
    - path/to/program_1.vrl
```

Migrate `files` by replacing:

```yaml
type: remap
files:
  - path/to/program_1.vrl
  - path/to/program_2.vrl
```

with:

```yaml
type: remap
source:
  type: disk
  files:
    - path/to/program_1.vrl
    - path/to/program_2.vrl
```
