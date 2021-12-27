# Docker container에서 resource제한하기

## memory 제한하기
```Shell
docker run -i -m 10m {이미지명:태그}
```

## CPU 제한하기
```Shell
docker run -i --cpus=0.5 python:3.8
```

## 사용되고 있는 resource확인하기
```Shell
docker stats
```

## 관련 docker docs
- https://docs.docker.com/config/containers/resource_constraints/
