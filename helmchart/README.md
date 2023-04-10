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
