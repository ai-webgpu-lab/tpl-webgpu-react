# Results

## 1. 실험 요약
- 저장소: tpl-webgpu-react
- 커밋 해시: 87b2478
- 실험 일시: 2026-04-22T06:55:20.176Z -> 2026-04-22T06:55:20.176Z
- 담당자: ai-webgpu-lab
- 실험 유형: `infra`
- 상태: `success`

## 2. 질문
- React shell 위에서도 capability probe와 canvas mount flow를 결과 문서로 고정할 수 있는가
- no-build React starter가 fallback 또는 WebGPU 경로를 명확히 기록하는가
- 후속 React 기반 실험 저장소의 첫 baseline으로 재사용 가능한가

## 3. 실행 환경
### 브라우저
- 이름: Chrome
- 버전: 147.0.7727.15

### 운영체제
- OS: Linux
- 버전: unknown

### 디바이스
- 장치명: Linux x86_64
- device class: `desktop-high`
- CPU: 16 threads
- 메모리: 16 GB
- 전원 상태: `unknown`

### GPU / 실행 모드
- adapter: WebGPU adapter
- backend: `webgpu`
- fallback triggered: `false`
- worker mode: `main`
- cache state: `unknown`
- required features: ["core-features-and-limits"]
- limits snapshot: {"maxTextureDimension2D":8192,"maxBindGroups":4,"maxBufferSize":268435456,"maxStorageBufferBindingSize":134217728}

## 4. 워크로드 정의
- 시나리오 이름: React WebGPU Starter
- 입력 프로필: react-no-build-static
- 데이터 크기: No-build React starter with capability panel and canvas mount flow.; automation=playwright-chromium
- dataset: -
- model_id 또는 renderer: -
- 양자화/정밀도: -
- resolution: 960x540
- context_tokens: -
- output_tokens: -

## 5. 측정 지표
### 공통
- time_to_interactive_ms: 1584.9 ms
- init_ms: 8.9 ms
- success_rate: 1
- peak_memory_note: 16 GB reported by browser
- error_type: Device was destroyed.

### Workload
- avg_fps: 60
- p95_frametime_ms: 16.7 ms
- scene_load_ms: 8.9 ms
- fallback states: false
- backends: webgpu

## 6. 결과 표
| Run | Scenario | Backend | Cache | Mean | P95 | Notes |
|---|---|---:|---:|---:|---:|---|
| 1 | React WebGPU Starter | webgpu | unknown | 60 | 16.7 | scene_load=8.9 ms, fallback=false |

## 7. 관찰
- starter backend는 webgpu이고 fallback_triggered=false로 기록됐다.
- frame pacing summary는 avg_fps=60, p95_frametime_ms=16.7였다.
- playwright-chromium로 수집된 automation baseline이며 headless=true, browser=Chromium 147.0.7727.15.
- 실제 runtime/model/renderer 교체 전 deterministic harness 결과이므로, 절대 성능보다 보고 경로와 재현성 확인에 우선 의미가 있다.

## 8. 결론
- React WebGPU starter도 첫 baseline raw result와 summary 문서를 갖게 됐다.
- 다음 단계는 build-driven React repo로 승격하면서 동일 결과 구조를 유지하는 것이다.
- 실제 app repo에서 state, worker, cache 경로를 덧붙여야 템플릿 검증이 완료된다.

## 9. 첨부
- 스크린샷: ./reports/screenshots/01-react-webgpu-starter.png
- 로그 파일: ./reports/logs/01-react-webgpu-starter.log
- raw json: ./reports/raw/01-react-webgpu-starter.json
- 배포 URL: https://ai-webgpu-lab.github.io/tpl-webgpu-react/
- 관련 이슈/PR: -
