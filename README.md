# Release
Update version (or versions) in `Chart.yaml`

```bash
helm push . tons --username $CHARTMUSEUM_AUTH_USER --password $CHARTMUSEUM_AUTH_PASS
```

# Deploy
Update version, for the given environment, in `helmfile.yaml`

```bash
helmfile -e prod sync
```
