## YAML 101

### Multi-line strings

#### `|`

엔터로 띄어 쓴 빈 줄을 `\n`으로 처리하며, 문자열 맨 마지막에 붙여준다

```yaml
example: |
  Hello
  Fast
  Campus.
# "Hello\nFast\nCampus.\n" 으로 처리
```



#### `>`

엔터로 띄어 쓴 스페이스로 처리하며, 문자열 맨 마지막에 `\n`을 붙여준다

```yaml
example: >
  Hello
  Fast
  Campus.
# "Hello Fast Campus.\n" 으로 처리
```



#### `|-` , `>-`

각각 `|`, `>` 와 동일하되, **문자열의 맨 마지막**에 `\n` 이 추가되지 않는다



### Multi-document yaml

`---` 구분선을 통해 하나의 yaml에 여러개의 docs 생성 가능

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: one
---
apiVersion: v1
kind: Service
metadata:
  name: two
---
apiVersion: v1
kind: Deployment
metadata:
  name: three
```








