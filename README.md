# SWE_2021_41_2024_2_week_6
---
## Week 4 Assignment
- [github.com/1102chlalstj/SWE_2021_41_2024_2_week_4](https://github.com/1102chlalstj/SWE_2021_41_2024_2_week_4)
```python
def isHappy(n):
    history = set()
    
    while n != 1 and n not in history:
        history.add(n)
        n = sum(int(digit) ** 2 for digit in str(n))

    return n == 1
```
- `history`: 계산된 수들을 저장하는 `set`. Cycle이 발생하는지 확인하기 위해 사용.
- `while` 반복문:
  - `n`이 `1`이 되면 종료. 이 경우, 주어진 숫자는 Happy Number.
  - `n`이 `history`에 존재하면 종료. 이 경우, 주어진 숫자는 Happy Number가 아님.
  - 현재 숫자 `n`을 `history`에 추가.
  - 숫자 `n`을 문자열로 변환하고, 각 자릿수를 따로 제곱한 뒤 합을 계산.
- `n`이 `1`이 되면 `True`, 그렇지 않으면 `False`를 반환.
---
## Week 5 Assignment
>```bash
>docker exec ossp-container cat /etc/os-release
>```
>- `docker exec`: Docker 컨테이너 내부에서 명령어를 실행할 때 사용하는 명령어.
>- `ossp-container`: 명령어를 실행할 대상이 되는 컨테이너 이름.
>- `cat /etc/os-release`: 컨테이너 내부에서 실행할 명령어. `/etc/os-release` 파일의 내용을 출력하는 명령어. 해당 파일은 시스템의 운영체제 정보를 포함.
>
>__Output:__
>```
>PRETTY_NAME="Ubuntu 24.04.1 LTS"
>NAME="Ubuntu"
>VERSION_ID="24.04"
>VERSION_CODENAME=noble
>ID=ubuntu
>ID_LIKE=debian
>HOME_URL="https://www.ubuntu.com/"
>SUPPORT_URL="https://help.ubuntu.com/"
>BUG_REPORT_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
>UBUNTU_CODENAME=noble
>LOGO=ubuntu-logo
>```

>```bash
>docker exec ossp-container git --version
>```
>- `docker exec`: Docker 컨테이너 내부에서 명령어를 실행할 때 사용하는 명령어.
>- `ossp-container`: 명령어를 실행할 대상이 되는 컨테이너 이름.
>- `git --version`: 컨테이너 내부에서 실행할 명령어. Git의 버전을 확인하는 명령어.
>
>__Output:__
>```
>git version 2.43.0
>```

>```bash
>docker exec ossp-container python3 --version
>```
>- `docker exec`: Docker 컨테이너 내부에서 명령어를 실행할 때 사용하는 명령어.
>- `ossp-container`: 명령어를 실행할 대상이 되는 컨테이너 이름.
>- `python3 --version`: 컨테이너 내부에서 실행할 명령어. Python3의 버전을 확인하는 명령어.
>
>__Output:__
>```
>Python 3.12.3
>```

>```bash
>docker inspect --format="{{ .HostConfig.Binds }}" ossp-container
>```
>- `docker inspect`: 지정된 Docker 컨테이너의 세부 정보를 출력하는 명령어.
>- `--format="{{ .HostConfig.Binds }}"`: `docker inspect` 명령어의 출력 결과를 특정 형식으로 출력하도록 지정하는 옵션. `{{ .HostConfig.Binds }}`는 `HostConfig` 섹션에서 `Binds`라는 필드에 해당하는 정보를 출력. `Binds`는 호스트 시스템의 디렉토리와 컨테이너 내부의 디렉토리 간 바인딩(마운트된 볼륨)을 나타냄.
>- `ossp-container`: 명령어를 실행할 대상이 되는 컨테이너 이름.
>
>__Output:__
>```
>[C:/Users/pc/ossp_host_dir:/mnt/ossp_container_dir]
>```
