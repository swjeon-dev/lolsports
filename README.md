# lolsports (초안)

e스포츠 데이터를 기반으로 실시간 UI와 데이터 시각화 경험을 구현하기 위해 제작 중인 프로젝트입니다.

[Fotmob](https://www.fotmob.com/ko)의 정보 구조를 참고하여
e스포츠 데이터에 맞는 형태로 재구성할 예정입니다.

LCK/LPL 경기 일정, 팀 정보, 선수 데이터 등을 기반으로
실시간 상태 처리와 데이터 시각화 중심 UI 구현을 목표로 하고 있습니다.

---

# 프로젝트 배경

데이터 시각화와 실시간 UI/UX에 관심이 있었고,
이를 가장 흥미롭게 표현할 수 있는 주제로 e스포츠 데이터를 선택했습니다.

특히 League of Legends e스포츠는:

- 경기 상태 변화가 빠르고
- 실시간 데이터 요소가 많으며
- 다양한 통계 지표를 제공하기 때문에

차트, 비교 UI, 실시간 상태 처리 등
프론트엔드 관점의 시각화 경험을 구현하기에 적합하다고 판단했습니다.

이 프로젝트는 단순 정보 제공보다:

- 데이터를 어떻게 구조화할 것인지
- 실시간 상태를 어떻게 표현할 것인지
- 복잡한 데이터를 어떻게 UI로 변환할 것인지

에 집중하여 설계하고 있습니다.

---

# 주요 기능

## 경기 일정

- LCK/LPL 경기 일정 조회
- LIVE 경기 상태 표시
- 경기 결과 확인

## 리그 순위

- 팀 standings 제공
- 승률 및 최근 경기 폼 확인

## 선수 데이터

- KDA
- 킬 관여율
- DPM
- Champion Pool

## 팀 정보

- 로스터
- 최근 경기
- 팀 통계

## 데이터 시각화

- 골드 차이 그래프
- 경기 타임라인
- 선수/팀 비교 UI
- Radar Chart

---

# 기술 스택

## Frontend

- Next.js App Router
- TypeScript
- Tailwind CSS
- Zustand
- TanStack Query

## Visualization

- Recharts

## Realtime

- socket.io
- polling

## Animation

- Framer Motion

---

# 기술 선택 이유

## Next.js App Router

SSR, Streaming, Dynamic Routing 등
실시간 데이터 서비스 구조를 경험하기 위해 사용할 예정입니다.

---

## TanStack Query

실시간 경기 상태와 API 데이터를 효율적으로 관리하기 위해 사용할 예정입니다.

- API 캐싱
- polling
- staleTime 전략
- request dedupe

등 서버 상태 관리 구조를 적용하는 것을 목표로 하고 있습니다.

---

## Zustand

Redux 대비 가볍고 단순한 구조로:

- 필터 상태
- 선택된 리그
- UI 상태

등 전역 상태를 관리하기 위해 사용할 예정입니다.

---

## Recharts

React 환경에 친화적이며 비교적 빠르게 학습하여 사용할 수 있다고 판단했습니다.

또한:

- React Component 기반 구조
- Tailwind CSS와의 조합
- 비교적 쉬운 커스터마이징

등 프로젝트 방향과 잘 맞는다고 판단했습니다.

---

# 실시간 데이터 처리 방향

실제 e스포츠 데이터 API는 무료 플랜 제한으로 인해
모든 실시간 인게임 데이터를 제공하지 않습니다.

따라서:

- 경기 일정
- 팀 정보
- standings
- LIVE 상태

등은 실제 API를 사용하고,

일부 인게임 이벤트 데이터는:

- websocket 기반 mock event stream
- polling

구조를 활용하여 실시간 UI 형태로 구현할 예정입니다.

---

# 성능 최적화 계획

- Dynamic Import
- Skeleton UI
- Lazy Loading
- Chart Component 분리
- 이미지 최적화

등을 적용할 예정입니다.

특히 차트 기반 UI가 많은 구조를 고려하여:

- 초기 렌더링 비용 감소
- unnecessary render 최소화
- client component 분리

등을 중점적으로 고려하고 있습니다.

---

# 프로젝트 구조

Feature 기반 구조를 사용하여:

- 관심사 분리
- 유지보수성
- 재사용성

을 고려할 예정입니다.

---

# 프로젝트 방향성

이 프로젝트는:

- 데이터 구조를 UI로 어떻게 표현할 것인지
- 실시간 상태를 어떻게 시각적으로 전달할 것인지

에 집중하고 있습니다.

단순 API 출력이 아니라:

- 데이터 시각화
- 실시간 UX
- 상태 관리
- 인터랙션 중심 UI
