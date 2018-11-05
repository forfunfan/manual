---
refcn: chapter_00/command
refen: welcome/command
---
# 명령 행

## V2 레이

V2Ray에는 다음과 같은 명령 줄 매개 변수가 있습니다.

```shell
v2ray [-version] [-test] [-config=config.json] [-format=json]
```

어디에:

* `-version`: V2Ray 버전 만 인쇄 한 다음 종료하십시오.
* `테스트`: 구성을 테스트하고 오류를 출력 한 다음 종료하십시오.
* `-config`: 구성의 URI. Avilable 형식은 다음과 같습니다. 
  * 로컬 설정 파일의 경로. 상대 경로 또는 절대 경로 일 수 있습니다.
  * `"stdin :"`: 표준 입력에서 구성을 읽는 V2Ray를 나타냅니다. 발신자는 구성을 기록한 후에 표준 입력을 닫아야합니다.
  * 값은 `시작합니다. http : //` 또는 `https : //` (소문자) : V2Ray는 원격 주소에서 구성을로드하려고 시도합니다.
* `-체재`: 구성 형식. 선택 사항은 다음과 같습니다. 
  * `json`: JSON 형식입니다.
  * `pb` 또는 `protobuf`: protobuf 형식.

{% 힌트 스타일 = '정보'%}는 시 `-config` 지정하지 V2Ray 처음부터 설정을로드하려고 `config.json` 에 의해 지정된 디렉토리 후, 작업 디렉토리하에 [환경 변수](../configuration/env.md) `v2ray.location .asset`. {% endhint %}

## V2Ctl

V2Ctl에는 다음과 같은 명령 줄 매개 변수가 있습니다.

```shell
v2ctl <command> <options>
```

사용 가능한 명령은 다음과 같습니다. 각 명령에는 고유 한 옵션이 있습니다.

### 확인

`v2ctl verify [--sig = / path / to / sigfile] / file / to / verify`

V2Ray 바이너리의 서명을 확인합니다.

옵션 :

* `시그마`: 서명 파일의 경로. 기본값은 확인할 경로에 대한 ".sig"파일입니다.
* 첫 번째 인수 : 확인할 파일입니다.

### 구성

`v2ctl 구성`

옵션이 없습니다. 이 명령은 stdin에서 JSON 형식의 구성을 읽은 다음 해당 구성을 Protobuf 형식으로 stdout에 작성합니다.

### UUID

`v2ctl uuid`

옵션이 없습니다. 이 명령은 임의의 UUID를 인쇄합니다.