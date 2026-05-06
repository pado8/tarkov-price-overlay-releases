# Tarkov Price Overlay

타르코프(Escape from Tarkov) 게임 화면의 아이템 위에 마우스를 올리고 단축키를 누르면, **플리 마켓 / 상인 시세를 투명 오버레이로 표시**해주는 데스크톱 앱입니다.

> 이 레포는 **인스톨러 배포 전용**입니다. 소스코드는 비공개 레포에서 관리됩니다.

---

## 📥 다운로드

**[👉 최신 버전 (Releases)](https://github.com/pado8/tarkov-price-overlay-releases/releases/latest)**

각 릴리즈마다 두 가지 형태로 제공합니다:

| 파일 | 크기 | 설치 방식 | 추천 |
|------|------|------|------|
| `..._x64-setup.exe` | ~310MB | NSIS 인스톨러 (시작메뉴/제어판 등록) | 일반 사용 |
| `..._portable.zip` | ~450MB | ZIP 압축 풀고 바로 실행 (설치 X) | 베타 테스트 / 멀티 버전 / USB |

---

## 🛠️ 설치

### 방법 A: 인스톨러 (`setup.exe`)
1. `Tarkov Price Overlay_x.y.z_x64-setup.exe` 다운로드
2. **Windows SmartScreen 경고 시:** `추가 정보` → `실행`
   *(코드 사이닝 인증서가 없는 베타 빌드라 정상입니다)*
3. 설치 완료 후 시작 메뉴에서 **Tarkov Price Overlay** 실행

### 방법 B: 포터블 ZIP (`_portable.zip`)
1. `Tarkov Price Overlay_x.y.z_portable.zip` 다운로드
2. 원하는 폴더에 압축 풀기 (예: `D:\Programs\TarkovOverlay\`)
3. 풀린 폴더 안의 **`Tarkov Price Overlay.exe`** 더블클릭
4. 제거 시 폴더 통째로 삭제 — 레지스트리 흔적 없음
5. **여러 버전을 동시에 설치 가능** (각 버전을 다른 폴더에 풀면 됨)

---

## 🎮 사용법

| 동작 | 단축키/방법 |
|------|------|
| 가격 조회 | 게임 인벤토리 아이템 위에 마우스 올리고 **F2** |
| 카드 위치 이동 | 헤더(상단) 잡고 드래그 |
| 카드 유지 | 마우스를 카드 위에 올리면 안 사라짐 |
| 종료 | 헤더 우측 **✕** 버튼 |

설정(⚙)에서 변경 가능:
- 언어 (한국어 / English)
- 게임 모드 (PVP / PVE) — **본인 모드와 일치시키세요. 가격 다릅니다.**
- 단축키 (F2 외 다른 키 가능)
- 카드 표시 시간
- 캡처 영역 미세 조정

---

## ⚙️ 시스템 요구사항

- Windows 10 / 11 (x64)
- 인터넷 연결 (tarkov.dev API 사용)
- 약 700MB 디스크 공간 (PyTorch + EasyOCR 모델 포함)

---

## ⚠️ 주의 사항

- **첫 F2 호출**: OCR 모델 워밍업으로 5~15초 정도 걸립니다 (그 이후엔 1~2초).
- **백신 false positive**: PyInstaller로 번들된 `.exe`라 일부 백신이 의심할 수 있습니다. 예외 등록이 필요할 수 있어요.
- **고DPI / 듀얼 모니터**: 환경에 따라 캡처 영역이 안 맞을 수 있습니다 → 설정 → 캡처 영역 → 수정.

---

## 🐛 버그 / 피드백

[Issues 탭](https://github.com/pado8/tarkov-price-overlay-releases/issues)에 다음을 포함해 남겨주세요:

- 사용 중인 OS / 게임 해상도
- 카드에 뜬 메시지 또는 콘솔 로그 캡처
- 작업 관리자에 `tarkov-server.exe`가 살아있는지 여부

---

## 📜 라이선스 / 면책

- 가격 데이터: [tarkov.dev](https://tarkov.dev) 공개 GraphQL API 사용
- 본 도구는 화면 캡처(OCR) 방식으로만 동작하며, 게임 메모리에 일절 접근하지 않습니다
- BattleState Games / EFT 게임 클라이언트와 무관한 비공식 도구입니다
