# ClipIyagi (클립이야기) v1.7.0

Windows와 Linux에서 사용할 수 있는 **가볍고 빠른 클립보드 히스토리 관리자**입니다.

복사한 텍스트와 이미지를 자동으로 저장하고, 전역 단축키로 언제든지 목록을 열어 빠르게 다시 붙여넣을 수 있습니다.

---

## ✨ 주요 기능

### 클립보드 관리
* **자동 저장** — 복사한 텍스트·이미지 자동 기록
* **핀 고정** — 중요한 항목을 목록 상단에 고정 (삭제 자동 정리 제외)
* **항목 편집** — 저장된 텍스트 내용 직접 수정
* **카테고리/태그** — 항목에 태그 설정, `#태그명` 으로 검색
* **최대 보관 개수** — 100 / 300 / 500 / 1000 / 무제한 선택

### 사용 편의
* **전역 단축키** — 어디서든 클립보드 목록 열기 (`Ctrl+Shift+V` 또는 `Ctrl+\``)
* **자동 붙여넣기** — 항목 선택 시 이전 창에 즉시 붙여넣기
* **붙여넣기 단축키 선택** — `Ctrl+V` (일반) / `Ctrl+Shift+V` (터미널 포함 전용도)
* **숫자 단축키** — `1~9`, `0` 키로 바로 선택 및 붙여넣기
* **실시간 검색** — 텍스트 내용 실시간 필터링
* **이미지 미리보기** — 썸네일에 마우스를 올리면 원본 팝업
* **무한 스크롤** — 대용량 히스토리도 부드럽게 탐색
* **창 크기 조절** — 원하는 크기로 자유롭게 조절

### 외관 설정
* **다크 모드** — 라이트/다크 테마 전환
* **폰트 크기 조절** — 9 / 10 / 12 / 14pt 선택

### 시스템
* **시스템 트레이 상주** — 트레이 아이콘으로 항상 접근 가능
* **자동시작** — 로그인 시 자동 실행 설정

---

## 🎮 단축키

| 키 | 기능 |
|---|---|
| Ctrl + Shift + V | 클립보드 목록 열기 |
| Ctrl + ` | 클립보드 목록 열기 |
| 1 ~ 9 / 0 | 해당 번호 항목 즉시 붙여넣기 |
| ESC | 목록 닫기 / 검색어 지우기 |
| 우클릭 | 핀 고정 · 편집 · 태그 · 삭제 메뉴 |

---

## ⬇ 다운로드

### Windows
Microsoft Store에서 설치합니다.
(스토어 링크 추가 예정)

### Linux
GitHub Releases에서 실행 파일을 다운로드합니다.

```bash
chmod +x ClipIyagi
./ClipIyagi
```

---

## 🐧 Linux 설치 참고

### Wayland (GNOME) — 자동 붙여넣기 사용 시

```bash
# 패키지 설치
sudo apt install ydotool wl-clipboard

# uinput 권한 설정 (최초 1회)
echo 'KERNEL=="uinput", GROUP="input", MODE="0660"' | sudo tee /etc/udev/rules.d/60-uinput.rules
sudo udevadm control --reload-rules && sudo udevadm trigger

# ydotoold 자동시작 등록 (권장)
mkdir -p ~/.config/systemd/user
cat > ~/.config/systemd/user/ydotoold.service << 'EOF'
[Unit]
Description=ydotool daemon
[Service]
ExecStart=/usr/bin/ydotoold
Restart=always
[Install]
WantedBy=default.target
EOF
systemctl --user enable --now ydotoold.service
```

### X11

```bash
sudo apt install xdotool
```

---

## 🖥 지원 플랫폼

* Windows 10 / 11
* Linux (GNOME Wayland / X11)

---

## 👤 개발자

IYAGI INC
Email: [iyagicom@gmail.com](mailto:iyagicom@gmail.com)
GitHub: https://github.com/iyagicom

---

## 📜 라이선스

Copyright (c) 2026 IYAGI INC. All rights reserved.

이 소프트웨어는 **실행 파일 형태로만 제공됩니다.** 소스 코드는 공개되지 않습니다.

개인적 및 비상업적 용도로 사용할 수 있습니다.
작성자의 명시적 서면 허가 없이 재배포, 수정, 리버스 엔지니어링을 금지합니다.
