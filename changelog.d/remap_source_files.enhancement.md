Improved the UX for the `remap` transform's mutually exclusive source fields. In addition to the
inline string form, `source` now accepts a `type`-tagged object selecting where the program comes
from: `type: vrl` for an inline `program`, or `type: disk` to load `files`:

```yaml
transforms:
  my_remap:
    type: remap
    source:
      type: disk
      files:
        - path/to/program_1.vrl
        - path/to/program_2.vrl
```

Existing configs continue to work, including the inline `source: '...'` shorthand. The top-level
`file` and `files` fields are now deprecated in favor of `source` with `type: disk`, but remain
functional and emit a deprecation warning at startup.

authors: pront
