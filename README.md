# helmfile-bug

State values not treating "yes" and "no" as boolean values in gotmpl files

To reproduce this issue. Run `helmfile template` from the root of the project.

```bash
$ helmfile template
Building dependency release=foo, chart=charts/foo
Templating release=foo, chart=charts/foo
---
# Source: foo/templates/test.yaml
ifResult: if evaluated to TRUE with .Values.flag=no
```

The correct output should be `ifResult: if evaluated to FALSE with .Values.flag=no`
