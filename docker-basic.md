## Docker 101

### FROM

Dockerfile의 base img를 명시한다

```dockerfile
FROM <image>[:tag] [AS name]

FROM ubuntu
FROM ubuntu:20.04
FROM nginx:latest AS ngx
```



### COPY

src 파일 or 디렉토리를 destination 경로에 복사

```dockerfile
COPY <src>... <dest>

COPY a.txt /some-directory/b.txt
COPY my-directory /some-directory-2
```



### RUN

명시된 커맨드가 도커 컨테이너에서 실행

```dockerfile
RUN <command>
RUN ["executable-command", "parameter1", "parameter2"]

# 예시
RUN pip install torch
RUN pip install -r requirements.txt
```



### CMD

명시된 커맨드가 도커 컨테이너 **실행 시 ** 실행

- 하나의 이미지에는 하나의 CMD 명령어만 실행할 수 있음

```dockerfile
CMD <command>
CMD ["executable-command", "parameter1", "parameter2"]
CMD ["parameter1", "parameter2"] # ENTRYPOINT 와 함께 사용될 때

# 예시
CMD python main.py
```



### WORKDIR

컨테이너 내 디렉토리를 지정하고, 그곳에서 Dockerfile에 기술했던 명령어가 수행

```dockerfile
WORKDIR /path/workspace
```



### ENV

컨테이너 내부에서 지속적으로 사용될 env variable 값을 설정

- 여기서 시간 설정도 KST 로 변경할 수 있을까?

```dockerfile
ENV <key> <value>
ENV <key>=<value>

# 예시
# default 언어 설정
RUN locale-gen ko_KR.UTF-8
ENV LANG ko_KR.UTF-8
ENV LANGUAGE ko_KR.UTF-8
ENV LC_ALL ko_KR.UTF-8
```



### EXPOSE

컨테이너의 port/protocol 지정, protocol 미지정 시 디폴트 TCP로 설정

```dockerfile
EXPOSE <port>/<protocol>
EXPOSE <port>
```
