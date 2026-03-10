# ClipIyagi (클립이야기)

> 클립보드 히스토리 관리자 — Windows / Linux (GNOME) 지원

텍스트·이미지를 자동으로 저장하고, 단축키 한 번으로 목록을 열어 빠르게 붙여넣을 수 있습니다.

---

## 기능

- **클립보드 자동 저장** — 텍스트·이미지 모두 기록
- **전역 단축키** — `Ctrl+Shift+V` 또는 `Ctrl+`` 으로 어디서나 열기
- **자동 붙여넣기** — 항목 선택 즉시 이전 창에 자동으로 붙여넣기
- **숫자 단축키** — 목록이 열린 상태에서 `1`~`9`, `0` 으로 바로 선택
- **검색** — 텍스트 내용 실시간 검색
- **이미지 미리보기** — 썸네일 위에 마우스를 올리면 원본 팝업
- **무한 스크롤** — 대량 히스토리도 빠르게 탐색
- **시스템 트레이** 상주

---

## 빌드

### 요구사항

| 항목 | 버전 |
|------|------|
| Qt | 6.x (Core, Widgets, Gui, DBus) |
| CMake | 3.16 이상 |
| 컴파일러 | GCC / MSVC / MinGW |

## Linux 설치 가이드

### 필수 패키지

```bash
sudo apt install ydotool wl-clipboard xdotool
```

| 패키지 | 용도 |
|--------|------|
| `ydotool` | Wayland에서 자동 붙여넣기 (Ctrl+V 전송) |
| `wl-clipboard` | Wayland에서 클립보드 유지 (`wl-copy`) |
| `xdotool` | X11 세션에서 자동 붙여넣기 |

> **Fedora / Arch** 계열은 `dnf` / `pacman` 으로 동일한 패키지명으로 설치하면 됩니다.

---

### Wayland (GNOME) 추가 설정 — 자동 붙여넣기용

ydotool은 커널 input 레벨에서 동작하므로 **input 그룹 추가 + 재로그인** 이 필요합니다.

```bash
# 1. input 그룹에 추가 (최초 1회)
sudo usermod -a -G input $USER

# 2. 재로그인 후 ydotoold 데몬 시작
ydotoold &
```

> 재부팅 후에도 자동 붙여넣기를 쓰려면 매번 `ydotoold &` 를 실행하거나,
> `~/.bashrc` 등에 추가해 두세요.

---

### 전역 단축키 (GNOME Wayland)

GNOME Wayland에서는 앱 실행 시 **gsettings 커스텀 단축키**가 자동 등록됩니다.
별도 설정 없이 `Ctrl+Shift+V` (또는 트레이에서 선택한 단축키)를 사용할 수 있습니다.

동작 방식:
1. 단축키 → 두 번째 ClipIyagi 인스턴스 실행
2. D-Bus로 실행 중인 첫 번째 인스턴스에 Toggle 신호 전달
3. 창 토글

---

## 플랫폼별 지원 현황

### ✅ Windows

| 기능 | 상태 |
|------|------|
| 클립보드 감시 | ✅ |
| 전역 단축키 | ✅ (`Ctrl+Shift+V` / `Ctrl+\``) |
| 자동 붙여넣기 | ✅ |
| 시스템 트레이 | ✅ |
| 자동 시작 | ✅ (레지스트리) |

---

### ✅ Linux — GNOME Wayland (Ubuntu 22.04+)

| 기능 | 상태 | 비고 |
|------|------|------|
| 클립보드 감시 | ✅ | |
| 전역 단축키 | ✅ | gsettings 자동 등록 |
| 자동 붙여넣기 | ✅ | `ydotool` + `wl-copy` 필요 |
| 시스템 트레이 | ✅ | XCB XEMBED (raw) |
| 자동 시작 | ⚠️ | 수동 등록 필요 |

#### ⚠️ GNOME Wayland에서 동작하지 않는 것

| 도구 | 이유 |
|------|------|
| `xdotool` | `_NET_ACTIVE_WINDOW` 미지원 — 활성 창 감지 불가 |
| `wtype` | GNOME이 `zwp_virtual_keyboard_v1` 프로토콜 미지원 |

→ 자동 붙여넣기는 반드시 `ydotool` + `ydotoold` 데몬을 사용해야 합니다.

---

### ⚠️ Linux — KDE / 기타 Wayland

전역 단축키가 동작하지 않을 수 있습니다. (GNOME gsettings 방식으로 등록하기 때문)
트레이 아이콘 클릭으로는 정상 사용 가능합니다.

---

### ✅ Linux — X11 세션

| 기능 | 상태 | 비고 |
|------|------|------|
| 클립보드 감시 | ✅ | |
| 전역 단축키 | ✅ | XCB hotkey grab |
| 자동 붙여넣기 | ✅ | `xdotool` 필요 |
| 시스템 트레이 | ✅ | |

---
