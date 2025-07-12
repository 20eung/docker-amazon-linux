# Amazon Linux에 Docker 설치하기

이 문서는 Amazon Linux에 Docker를 설치하는 방법을 안내합니다.

## 1. 패키지 업데이트

시스템의 패키지를 최신 상태로 업데이트합니다.

```bash
sudo yum update -y
```

## 2. Docker 설치

`yum` 패키지 관리자를 사용하여 Docker를 설치합니다.

```bash
sudo yum install -y docker
```

## 3. Docker 서비스 시작

Docker 데몬을 시작합니다.

```bash
sudo systemctl start docker
```

## 4. 사용자 권한 설정

`sudo` 없이 Docker 명령을 실행할 수 있도록 현재 사용자를 `docker` 그룹에 추가합니다. `ec2-user`는 사용하는 사용자 이름으로 변경해야 할 수 있습니다.

```bash
sudo usermod -a -G docker ec2-user
```

**참고:** 사용자 그룹 변경 사항을 적용하려면 로그아웃했다가 다시 로그인해야 합니다.

## 5. 설치 확인

Docker가 성공적으로 설치되고 실행 중인지 확인합니다.

```bash
docker ps
```

## 6. Docker Compose 설치

다음 명령어를 실행하여 Docker Compose를 다운로드하고 실행 권한을 부여합니다.

```bash
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

## 7. Docker Compose 설치 확인

Docker Compose가 성공적으로 설치되었는지 버전을 확인합니다.

```bash
docker-compose --version
```
