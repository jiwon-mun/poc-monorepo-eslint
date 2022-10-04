# poc-monorepo-eslint

## 독립 하는 이유 및 방법

### 이유 및 문제점

사용이 좀 더 단순하고 용이함.
근데 IDE에서 같은 설정을 유지 할 수 없음. ( eslint vscode server는 root프로젝트 .eslint 가 기본 default임. setting에서 설정 가능하나 Dynamic하게 설정은 안됨.)

### 방법

없음. 그냥 하면 됨

## 독립 하지 않는 이유 및 방법

### 이유

중앙 제어 가능함. 버전 통일을 할 필요가 없음. ( 애초에 버전이 하나라서 )
설정에 제약이 있음. 별개의 추가적인 스크립트 작업이 필요할 지도 모름 ( 특정 패키지만 eslint가 돌릴 방법이 필요. 이는 lint-staged를 활용하면 해결 될지도 모름 )

### 방법

`.eslintrc`에 `root` 프로퍼티를 사용해서 `hierarchy`를 만듬.

`package.json` 명령어는 `prevfix:command` 로 해서 전역 명령어로 사용 해야 함.

예를 들어

```
"root:lint": "eslint"
```
