# YAML Shared Library Examples

Self-contained examples that use only `echo` and `sh` steps (no Maven, npm, or other tool dependencies).

## Directory layout

```
remote-lib/                 Simulates a remote library (same format, referenced via git URL)
  library.yaml              Manifest with infra-focused exports
  steps/
    notify.yaml             Step export: notification steps
  stages/
    approval-gate.yaml      Stage export: input directive + post conditions

consumer-all-features.yaml Pipeline from yaml-jobs-demo using all three libraries, every control flow construct
consumer-pipeline-use.yaml Pipeline-level from yaml-jobs-demo use: (entire pipeline from library)
```

## How to test

These files can be loaded by the plugin's test harness via `type: local` repositories. To try manually:

1. Run `mvn hpi:run` from the plugin root
2. Create a Pipeline job in Jenkins at `localhost:8080/jenkins`
3. Paste `consumer-all-features.yaml` as the inline YAML
4. Adjust the `path:` values in `resources.repositories` to absolute paths on your machine
