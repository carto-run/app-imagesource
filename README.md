# app-imagesource

## Creating the Workload

```
tanzu apps workload create app-imagesource \
  --namespace dev \
  --source-image ghcr.io/carto-run/app-imagesource:latest \
  --label app.kubernetes.io/part-of=app-imagesource \
  --label apps.tanzu.vmware.com/has-tests=true \
  --type web \
  --yes
```

## Logs

```
tanzu apps workload tail app-imagesource
```

## Configuration

| Item            | Config                                                                                |
| --------------- | ------------------------------------------------------------------------------------- |
| Scan Policy     | [default](resources/scan-policy.yaml)                                                 |
| Pipeline        | [developer-defined-tekton-pipeline](resources/developer-defined-tekton-pipeline.yaml) |
| tap-values.yaml | na                                                                                    |
| Supply Chain    | source-test-scan-to-url                                                               |

