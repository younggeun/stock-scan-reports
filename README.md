# Korean Stock Scan Reports

Codex가 생성한 KOSPI·KOSDAQ 추세추종 스캐너의 **공개 시장 보고서 저장소**다.

보고서 보기: <https://younggeun.github.io/stock-scan-reports/>

## 무엇을 볼 수 있나

- 일간 종가 확정 스캔과 날짜별 과거 보고서
- 10시·14시 예약 및 수동 실행한 장중 잠정 미리보기
- 주간·월간 신호 요약
- Fresh Breakout 이후 +5/+10/+20거래일 Forward 성과
- 점수 등급·RS·VCP·신호별 실제 완료 표본 비교

이 보고서는 자동 주문이나 매수 추천이 아니다. 장중 신호는 미확정이며 공식 성과 통계에 들어가지 않는다.

## 공개 파일

| 파일 | 설명 |
|---|---|
| `index.html` | 모바일 보고서 UI |
| `dates.json` | 사용 가능한 종가 보고서 날짜 manifest |
| `reports/YYYY-MM-DD.json` | 해당 거래일의 공개 분석 결과 |
| `reports/YYYY-MM-DD.summary.json` | 이전 날짜 비교용 경량 데이터 |
| `performance.json` | 완료/대기 Forward 성과 |
| `intraday.json` | 최신 장중 잠정 결과 |
| `intraday.previous.json` | 직전 장중 잠정 결과 |
| `intraday-manifest.json` | 장중 비교 시점 목록 |
| `intraday/YYYY-MM-DD/*.json` | 장중 비교용 경량 요약 |

날짜별 JSON은 누적 보존한다. `index.html`은 경량 로더이며 선택한 날짜 데이터와 성과 데이터를 필요할 때 별도로 불러온다.

## 갱신 방식

- 정규 종가 스캔: KRX 거래일 평일 16:30 KST 이후
- 장중 미리보기: 거래일 10:00·14:00 KST 예약 및 수동 실행
- 주말·공휴일·연말 휴장일: 정규 보고서를 새로 만들지 않음

GitHub Actions 예약은 지연될 수 있다. commit 제목에는 종가 기준일과 게시 KST가 기록된다.

## 공개하지 않는 정보

이 저장소에는 Telegram/GitHub 토큰, 운영 DB, 개인 보유수량·매수가·메모를 게시하지 않는다. 생성 파일을 직접 수정하면 다음 자동 게시에서 일관성이 깨질 수 있으므로 원본 소스와 생성기를 수정한다.

분석 기준과 사용법은 비공개 소스 저장소의 문서 및 사이트 제목 옆 `ⓘ` 가이드를 기준으로 한다.
