<div align="center">

# 🤖 SmartConnector MQTT Simulator

**MQTT 기반 설비 시뮬레이터 for 스마트 팩토리**

[![Version](https://img.shields.io/badge/version-1.1.1-blue.svg)](https://github.com/ssb0498/SmartConnector-MQTT-Simulator-releases/releases)
[![Platform](https://img.shields.io/badge/platform-Windows-lightgrey.svg)](https://github.com/ssb0498/SmartConnector-MQTT-Simulator-releases/releases)

---

*설비(EQP)와 MCS 간의 MQTT 통신을 손쉽게 테스트하고 시뮬레이션할 수 있는 데스크탑 애플리케이션입니다.*

</div>

---

## 📋 목차

- [📥 설치 방법](#-설치-방법)
- [🚀 사용 방법](#-사용-방법)
- [⌨️ 단축키](#️-단축키)
- [💡 유용한 기능](#-유용한-기능)

---

## 📥 설치 방법

### 다운로드 및 설치

1. [Releases](https://github.com/ssb0498/SmartConnector-MQTT-Simulator-releases/releases)에서 최신 버전의 설치 파일을 다운로드합니다.

2. `SmartConnector MQTT Simulator Setup x.x.x.exe` 파일을 실행합니다.

3. 설치가 완료되면 자동으로 앱이 실행됩니다.

> 💡 **Tip**: 바탕화면과 시작 메뉴에 바로가기가 자동 생성됩니다.

---

## 🚀 사용 방법

### 1️⃣ 초기 설정

앱을 처음 실행하면 초기 설정 화면이 나타납니다.

| 항목 | 설명 | 예시 |
|------|------|------|
| MQTT Broker URL | MQTT 브로커 주소 | `mqtt://192.168.1.100:1883` |
| Publish Topic | 데이터 발행 토픽 | `factory/{facilityName}/data` |
| Publish Interval | 발행 주기 (초) | `1` |
| Facilities | 시뮬레이션할 설비 목록 | `EQ11`, `EQ12` |
| Tags | 관리할 태그 목록 | `Call_Request`, `EQ_Code_01` |

### 2️⃣ 메인 화면

<img width="1901" height="1030" alt="image" src="https://github.com/user-attachments/assets/f0bc36b9-5b12-4277-93d6-d94b0c8fe24b" />

- **왼쪽 컬럼**: 설비에서 MCS로 발행하는 태그
- **중앙 컬럼**: MCS에서 설비로 제어하는 태그
- **오른쪽 컬럼**: 미리 정의된 매크로 버튼

### 3️⃣ 태그 값 변경

| 타입 | 변경 방법 |
|------|----------|
| **Boolean** | 태그 카드를 클릭하면 `true` ↔ `false` 토글 |
| **Number/String** | 값 영역을 클릭 → 새 값 입력 → `Set` 클릭 |

### 4️⃣ 설정 변경

우측 상단의 **사이트 뱃지(⚙️)**를 클릭하여 설정 창을 열 수 있습니다.

설정 가능 항목:
- 설비 추가/삭제/그룹 지정
- 태그 추가/삭제/타입 변경
- 매크로 정의
- 트리거 규칙 설정
- 사이트 추가/전환/삭제

---

## ⌨️ 단축키

앱을 더욱 빠르게 사용할 수 있는 **전역 단축키**를 제공합니다.

| 단축키 | 기능 | 설명 |
|--------|------|------|
| `Ctrl + Shift + A` | **앱 활성화/비활성화** | 앱 창을 보이거나 숨깁니다. 다른 작업 중에도 빠르게 시뮬레이터에 접근! |
| `Ctrl + Shift + Q` | **설비 검색** | Spotlight 스타일의 검색창으로 설비를 빠르게 찾고 선택! |

> 🔥 **Pro Tip**: 트레이 아이콘을 클릭해도 앱을 보이거나 숨길 수 있습니다!

---

## 💡 유용한 기능

### 🔍 설비 검색 (Spotlight Search)

`Ctrl + Shift + Q`를 누르면 검색창이 나타납니다.

<img width="1275" height="710" alt="image" src="https://github.com/user-attachments/assets/e5027008-20ae-466a-ac48-982008086738" />


- 설비 이름 일부를 입력하면 **실시간 필터링**
- `↑` `↓` 키로 항목 이동
- `Enter`로 선택, `Esc`로 닫기

---

### 📌 트레이 아이콘

앱은 시스템 트레이에 상주하여 **백그라운드에서 계속 실행**됩니다.

| 동작 | 기능 |
|------|------|
| **클릭** | 앱 보이기/숨기기 |
| **우클릭** → `보이기/숨기기` | 창 토글 |
| **우클릭** → `종료` | 앱 완전 종료 |

---

### ⚡ 매크로 기능

자주 사용하는 동작을 매크로로 정의하여 **버튼 하나로 실행**할 수 있습니다.

**예시**: `LOAD` 매크로
```
동작 1: EQ_LOAD_REQ    → true
동작 2: EQ_LOAD_READY  → true
동작 3: EQ_STATUS      → LOADING
```

---

### 🎯 트리거 기능

특정 조건이 만족되면 **자동으로 동작을 실행**합니다.

**예시**: 로딩 완료 트리거
```
IF:   EQ_LOAD_COMPLETE = true
THEN: EQ_STATUS   → IDLE
      EQ_LOAD_REQ → false
```

---

### 🌐 다중 사이트 지원

여러 사이트(공장, 환경)의 설정을 저장하고 손쉽게 전환할 수 있습니다.

- ➕ 새 사이트 추가
- 📋 기존 설정을 복제하여 새 사이트 생성
- 🔄 사이트 간 빠른 전환

---

<div align="center">

**Made with ❤️ for Smart Factory**

</div>
