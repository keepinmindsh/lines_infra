# [Charts](https://helm.sh/docs/topics/charts/)

Helm은 charts로 불리는 Packaging 형식을 사용한다. 하나의 차트는 Kubernetes 자원의 연관된 구성을 가지고 있는 파일이다. 

만약 배포되어있는 차트 파일을 확인하고 싶은 경우, 아래의 명령어를 이용해서 다운로드 및 확인할 수 있다. 

```shell 
$ helm pull chartrepo/chartname
``` 

## 차트 파일의 구성도 

```shell
wordpress/
  Chart.yaml          # Helm Chart의 정보를 담고 있는 yaml 파일 
  LICENSE             # OPTIONAL: Chart의 라이선스 정보를 포함하고 있는 평문 파일 
  README.md           # OPTIONAL: A human-readable README file
  values.yaml         # 해당 Chart를 위한 기본 환경 값을 가지고 있음 
  values.schema.json  # OPTIONAL: A JSON Schema for imposing a structure on the values.yaml file
  charts/             # 해당 chart와 연관된 모든 차트를 가지고 있는 디렉토리 경로 
  crds/               # 사용자화한 자원 정의 목록 
  templates/          # 값을 사용해서 조합될 때 템플릿은 쿠버네티스 메니페스트 파일을 생성할 하는데, 해당 템플릿들을 저장해두는 폴더
  templates/NOTES.txt # OPTIONAL: 사용 방법을 포함하는 평문 파일 
```

## Chart.yaml 파일에 대해서 

각각의 항목에 대해서 명확히 이해해야함. 실제 필수 값과 옵션값의 설정을 확인해서 구성 필요. Helm Chart로 사용된 yaml에서 required 항목은 반드시 작성되어야 한다. 

```yaml 
apiVersion: The chart API version (required)
name: The name of the chart (required)
version: A SemVer 2 version (required)
kubeVersion: A SemVer range of compatible Kubernetes versions (optional)
description: A single-sentence description of this project (optional)
type: The type of the chart (optional)
keywords:
  - A list of keywords about this project (optional)
home: The URL of this projects home page (optional)
sources:
  - A list of URLs to source code for this project (optional)
dependencies: # A list of the chart requirements (optional)
  - name: The name of the chart (nginx)
    version: The version of the chart ("1.2.3")
    repository: (optional) The repository URL ("https://example.com/charts") or alias ("@repo-name")
    condition: (optional) A yaml path that resolves to a boolean, used for enabling/disabling charts (e.g. subchart1.enabled )
    tags: # (optional)
      - Tags can be used to group charts for enabling/disabling together
    import-values: # (optional)
      - ImportValues holds the mapping of source values to parent key to be imported. Each item can be a string or pair of child/parent sublist items.
    alias: (optional) Alias to be used for the chart. Useful when you have to add the same chart multiple times
maintainers: # (optional)
  - name: The maintainers name (required for each maintainer)
    email: The maintainers email (optional for each maintainer)
    url: A URL for the maintainer (optional for each maintainer)
icon: A URL to an SVG or PNG image to be used as an icon (optional).
appVersion: The version of the app that this contains (optional). Needn't be SemVer. Quotes recommended.
deprecated: Whether this chart is deprecated (optional, boolean)
annotations:
  example: A list of annotations keyed by name (optional).
```
