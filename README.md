# Release
Update version (or versions) in `Chart.yaml`

```bash
helm package --sign --key 'sj' .

curl --user $CHARTMUSEUM_AUTH_USER:$CHARTMUSEUM_AUTH_PASS \
  -F "chart=@surf-screenshotter-$version.tgz" \
  -F "prov=@surf-screenshotter-$version.tgz.prov" \
  https://helm-charts.fitfit.dk/api/charts
```

Commit and tag commit: RELEASE-$version

# Deploy
Update version, for the given environment, in `helmfile.yaml`

```bash
helmfile -e prod sync
```
