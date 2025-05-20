# myDocker

Ubuntu 22.04 기반 개발용 도커 환경 이미지. 다음과 같은 구성 요소 포함:

## 기본 정보

* Base Image: `ubuntu:22.04`
* 사용자 계정: `dev` (uid/gid: 1000)
* 작업 디렉토리: `/home/dev/workspace`
* 이미지명: `nowage/docker`

## 주요 패키지

* 필수 도구
  - `sudo`, `curl`, `wget`, `git`, `vim`, `tmux`, `zsh`
  - `python3`, `pip`, `python3-venv`, `build-essential`
* 개발 환경
  - Docker CLI
  - Node.js / npm (설치된 경우)
* 네트워크 / 시스템 도구
  - `iputils-ping`, `net-tools`, `htop`, `psmisc`

## 사용자 정보

* 사용자명: `dev`
* 홈 디렉토리: `/home/dev`
* 초기 작업 디렉토리: `/home/dev/workspace`

## 사용 예시

```bash
# docker build
docker build -t nowage/docker .

# docker run
docker run -it --rm \
  -v $(pwd):/home/dev/workspace \
  nowage/docker
