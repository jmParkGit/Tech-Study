# Please re-run gsutil config and make sure to follow the instructions forfinding and entering your default project id.
## 에러로그
```shell
student_01_dfbb10814a67@cloudshell:~$ gsutil mb gs://example-coursera99_2
Creating gs://example-coursera99_2/...
You are attempting to perform an operation that requires a project id, with none configured. Please re-run gsutil config and make sure to follow the instructions forfinding and entering your default project id.
```

## 원인
- config 정보에 project_id가 없어서 일어나는 현상
```shell
student_01_dfbb10814a67@cloudshell:~$ gcloud config list
[accessibility]
screen_reader = True
[component_manager]
disable_update_check = True
[compute]
gce_metadata_read_timeout_sec = 30
[core]
account = student-01-dfbb10814a67@qwiklabs.net
disable_usage_reporting = True
[metrics]
environment = devshell
```

## 해결책
- project_id 추가
```shell
gcloud config set core/project <value>
```
```shell
student_01_dfbb10814a67@cloudshell:~ (qwiklabs-gcp-03-db7c9da788fa)$ gcloud config list
[accessibility]
screen_reader = True
[component_manager]
disable_update_check = True
[compute]
gce_metadata_read_timeout_sec = 30
[core]
account = student-01-dfbb10814a67@qwiklabs.net
disable_usage_reporting = True
project = qwiklabs-gcp-03-db7c9da788fa
[metrics]
environment = devshell
```

## 결과
- project_id 추가 후, 정상적으로 gsutil 커맨드 실행됨

## reference
- https://github.com/google-github-actions/setup-gcloud/pull/68
