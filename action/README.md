# Sync Kubrenetes images

## Usage

```yaml
name: sync kubrenetes images

on:
  workflow_dispatch: # 手动触发
  schedule:
  - cron: 0 */6 * * *

jobs:
  sync-k8s-image:
    name: sync kubrenetes images
    runs-on: ubuntu-latest
    steps:
    - name: sync
      uses: ameizi/sync-k8s-images/action@master
      with:
        username: ${{ secrets.DOCKER_USERNAME }}
        password: ${{ secrets.DOCKER_PASSWORD }}
        repository: v5cn
        kubernetes_version: v1.19.7
```
