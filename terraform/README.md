# Terraform 

테라폼은 코드로 인프라를 관리할 수 있는 도구 입니다. 

## Hello! Terraform

### MacOS 기준 Terraform 

- Terraform 설치하기 

```shell
$ brew install terraform 
```

- Terraform 버전체크 

```shell
$ terraform -version
Terraform v1.3.8
on darwin_arm64
```

- GCP Terraform 계정 만들기 

GCP의 Service Account을 Terraform을 기준으로 생성한다. 

![Terraform Service Account](https://github.com/keepinmindsh/lines_infra/blob/main/terraform/terraform-account.png)

## Terraform Install 

```shell
$ terraform -help plan
```

```shell
$ terraform -install-autocomplete
```

## Terraform Get Started 

```yaml
terraform {
  required_providers {
    docker = {
      source  = "kreuzwerker/docker"
      version = "~> 2.13.0"
    }
  }
}

provider "docker" {}

resource "docker_image" "nginx" {
  name         = "nginx:latest"
  keep_locally = false
}

resource "docker_container" "nginx" {
  image = docker_image.nginx.latest
  name  = "tutorial"
  ports {
    internal = 80
    external = 8000
  }
}
```

```shell
$ terraform init 
```

```shell
$ terraform plan 
```

```shell
$ terraform apply 
```

```shell
$ terraform destroy
```

```shell
$ terraform fmt
```

```shell
$ terraform validate
Success! The configuration is valid.
```
> [VPC Network 구성](https://spacek82.tistory.com/60)  
> [Terraform 해보기](https://jh3859025.medium.com/terraform-gcp-vm%EC%9D%B8%EC%8A%A4%ED%84%B4%EC%8A%A4-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0-b9799585d1a)

## Provider 

### Kafka 

- [Kafka's Provider](https://registry.terraform.io/providers/Mongey/kafka/latest/docs)

## Terraform 공부 자료 

- [Terraform Study 자료](https://developer.hashicorp.com/terraform/language/expressions/types)

## 사용할때 체크해야할 사항 

- [Google Cloud - Terraform 사용 권장사항](https://cloud.google.com/docs/terraform/best-practices-for-terraform?hl=ko)
- [Module 단위 Terraform 구성시 검토사항](https://developer.hashicorp.com/terraform/language/modules/develop/composition)