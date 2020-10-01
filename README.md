# Release
Update version (or versions) in `Chart.yaml`

```bash
export CHART_VERSION=0.6.0

helm package --sign --key 'sj' .

curl --user $CHARTMUSEUM_AUTH_USER:$CHARTMUSEUM_AUTH_PASS \
  -F "chart=@surf-screenshotter-$CHART_VERSION.tgz" \
  -F "prov=@surf-screenshotter-$CHART_VERSION.tgz.prov" \
  https://helm-charts.fitfit.dk/api/charts

rm surf-screenshotter-$CHART_VERSION.tgz*
```

Commit and tag commit: RELEASE-$CHART_VERSION
```bash
git ci -m 'Bump version'
git tag RELEASE-$CHART_VERSION
git push
git push --tags
```

# Development
```bash
skaffold dev
```
