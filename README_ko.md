# ClipIyagi (클립이야기)

Windows와 Linux에서 사용할 수 있는 **가볍고 빠른 클립보드 히스토리 관리자**입니다.

ClipIyagi는 복사한 **텍스트와 이미지**를 자동으로 저장하고,
전역 단축키로 언제든지 목록을 열어 빠르게 다시 붙여넣을 수 있습니다.

---

## ✨ 주요 기능

* **클립보드 자동 저장** — 복사한 텍스트와 이미지 자동 기록
* **전역 단축키** — 어디서든 클립보드 목록 열기
* **자동 붙여넣기** — 항목 선택 시 이전 창에 즉시 붙여넣기
* **숫자 단축키** — `1~9`, `0` 키로 바로 선택 및 붙여넣기
* **검색 기능** — 텍스트 내용 실시간 검색
* **이미지 미리보기** — 썸네일에 마우스를 올리면 원본 팝업
* **무한 스크롤** — 많은 히스토리도 빠르게 탐색
* **시스템 트레이 상주**

---

## ⚡ 빠른 실행 (Linux)

Linux 실행 파일을 다운로드한 후 실행합니다.

```bash
chmod +x clipiyagi
./clipiyagi
```

---

## 🖥 지원 플랫폼

지원 운영체제

* Windows
* Linux (GNOME / X11)

---

## ⬇ 다운로드

### Linux

GitHub Releases에서 실행 파일을 다운로드합니다.

다운로드 후 실행:

```bash
chmod +x clipiyagi
./clipiyagi
```

---

### Windows

Microsoft Store에서 설치합니다.

(스토어 링크 추가 예정)

---

## 🎮 단축키

| 키                | 기능             |
| ---------------- | -------------- |
| Ctrl + Shift + V | 클립보드 목록 열기     |
| Ctrl + `         | 클립보드 목록 열기     |
| 1~9 / 0          | 선택한 항목 즉시 붙여넣기 |
| ESC              | 목록 닫기          |

---

## 🐧 Linux 참고사항

Linux 환경에서는 일부 자동화 기능을 위해 추가 패키지가 필요할 수 있습니다.

### Wayland (GNOME)

필수 패키지 설치

```bash
sudo apt install ydotool wl-clipboard
```

ydotool 데몬 실행

```bash
ydotoold &
```

---

### X11

필수 패키지 설치

```bash
sudo apt install xdotool
```

---

## 📌 참고

* 시스템 트레이에서 실행됩니다
* 클립보드 히스토리를 자동 저장합니다
* 설정은 자동으로 저장됩니다
* 텍스트와 이미지 모두 지원합니다

---

## 👤 개발자

IYAGI INC
Email: [iyagicom@gmail.com](mailto:iyagicom@gmail.com)
GitHub: https://github.com/iyagicom

---

## 📜 라이선스

Copyright (c) 2026 IYAGI INC

All rights reserved.

이 소프트웨어는 **실행 파일 형태로만 제공됩니다.**
소스 코드는 공개되지 않습니다.

개인적 및 비상업적 용도로 사용할 수 있습니다.

작성자의 명시적 서면 허가 없이
재배포, 수정, 리버스 엔지니어링을 금지합니다.
