# tpl-webgpu-react

`React 기반 실험 템플릿`를 위한 출발점 템플릿 저장소입니다. 새로운 실험/벤치/앱 저장소를 만들기 전에 가장 얇은 실행 경로와 결과 구조를 먼저 검증하는 기준선 역할을 합니다.

## 저장소 역할
- 새 저장소가 바로 가져갈 수 있는 최소 디렉터리 구조와 결과 리포팅 규칙을 제공합니다.
- WebGPU 기능 감지, 실패 표면, 기본 렌더/실행 루프 같은 공통 시작점을 정리합니다.
- 프레임워크 도입 전에 가장 단순한 baseline을 재현해 이후 비교 기준을 만듭니다.

## 핵심 질문
- 이 스택에서 가장 작은 성공 경로로 baseline 데모를 띄울 수 있는가
- capability 확인, 오류 메시지, fallback 기록을 어떤 구조로 남길 것인가
- 이후 실험/벤치 저장소가 공통으로 복제할 README/RESULTS 흐름은 무엇인가

## 포함 범위
- 최소 실행 예제와 기본 디렉터리 구조
- 결과 스키마, `RESULTS.md`, `reports/` 폴더 연결
- 첫 runnable baseline을 다른 저장소가 재사용할 수 있도록 문서화

## 비범위
- 도메인별 완성 기능이나 대규모 제품 UX
- 여러 런타임/모델/렌더러의 폭넓은 비교
- 템플릿 단계에서의 과도한 추상화

## 기본 구조
- `src/` - 구현 코드 또는 baseline 프로토타입
- `public/` - GitHub Pages baseline probe 또는 실제 정적 데모 산출물
- `reports/raw/` - 원시 측정 결과 JSON/CSV/로그
- `reports/screenshots/` - 시각 결과 스크린샷
- `reports/logs/` - 실행 로그와 디버깅 산출물
- `schemas/ai-webgpu-lab-result.schema.json` - 공통 결과 스키마
- `RESULTS.md` - 핵심 결과 요약과 해석

## 메타데이터
- Track: Infra
- Kind: infra
- Priority: P0

## 현재 상태
- Repository scaffold initialized
- Shared result schema copied to `schemas/ai-webgpu-lab-result.schema.json`
- Shared reporting template copied to `RESULTS.md`
- Repo-specific Pages baseline copied from `repo-scaffolds/p0/tpl-webgpu-react/`
- Generated entry point updated in `public/index.html` and related assets
- GitHub Pages workflow copied to `.github/workflows/deploy-pages.yml`

## 현재 baseline 상태
- Repository-specific runnable baseline active: no-build React WebGPU starter with capability panel, React mount flow, and live canvas sample
- Generated override source: `repo-scaffolds/p0/tpl-webgpu-react/`
- Results/report scaffold is ready to promote exported JSON into `reports/raw/` and `RESULTS.md`

## GitHub Pages 운영 메모
- Pages URL: https://ai-webgpu-lab.github.io/tpl-webgpu-react/
- 기본 bootstrap workflow는 `public/` baseline probe 정적 artifact를 배포합니다.
- 실제 빌드가 필요한 저장소는 install/build 단계와 artifact 경로를 저장소 사양에 맞게 교체해야 합니다.

## 조직 상태 대시보드
- 전체 Pages/demo 상태는 `docs-lab-roadmap/docs/PAGES-STATUS.md`에서 확인합니다.
- 이 저장소의 live demo는 `https://ai-webgpu-lab.github.io/tpl-webgpu-react/`입니다.
- 통합 sketch/adapter 상태는 `docs-lab-roadmap/docs/INTEGRATION-STATUS.md`에서 확인합니다.
- sketch capabilities는 `docs-lab-roadmap/docs/SKETCH-METRICS.md`에서 확인합니다.

## 측정 및 검증 포인트
- 첫 실행 성공 여부와 환경 재현성
- capability probe와 fallback 기록 가능 여부
- 템플릿에서 파생 저장소로 옮길 때 필요한 수정 범위

## 산출물
- 최소 실행 예제
- 복제 가능한 README/RESULTS 문서 구조
- GitHub Pages에서 확인 가능한 baseline surface

## 작업 및 갱신 절차
- `src/` 아래에 첫 runnable baseline 또는 비교 harness를 구현합니다.
- 실제 사용 스택이 정해지면 이 README에 install/dev/build/test 명령을 추가합니다.
- 측정 결과는 `reports/raw/`와 `RESULTS.md`에 함께 반영합니다.
- 브라우저, OS, 디바이스, cache, worker 여부 등 재현 조건을 결과와 같이 기록합니다.
- Pages를 유지하는 경우 baseline probe 또는 workflow를 실제 저장소 동작에 맞게 교체합니다.

## 완료 기준
- 새 저장소가 이 템플릿을 기준으로 바로 시작할 수 있습니다.
- 첫 baseline 실행 경로가 README에 정리되어 있습니다.
- 결과 스키마와 Pages baseline probe가 함께 연결되어 있습니다.

## 관련 저장소
- `shared-webgpu-capability` - capability 수집 유틸
- `shared-bench-schema` - 결과 스키마와 결과 템플릿
- `docs-lab-roadmap` - 템플릿이 따라야 할 운영 기준

## 라이선스
MIT
