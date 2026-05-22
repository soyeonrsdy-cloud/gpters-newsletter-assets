# GPTers Newsletter Assets

GPTers 뉴스레터(스티비 발송용) 이미지 호스팅 public CDN. 매 호별 폴더에 이미지를 넣고 push하면 GitHub raw URL로 이메일에 임베드된다.

## 폴더 구조

```
gpters-newsletter-assets/
├── 27/                # 27호 (2026-05-22)
│   ├── hero.jpg       # 헤더 이미지 (1280x640, ~250KB)
│   ├── banner-23gi.png  # 23기 스터디 배너 (1280x360)
│   └── banner-b2b.png   # B2B 교육 배너 (1280x360)
├── 28/                # 28호
└── ...
```

## URL 패턴

```
https://raw.githubusercontent.com/soyeonrsdy-cloud/gpters-newsletter-assets/main/{호번호}/{파일명}
```

예시:
```
https://raw.githubusercontent.com/soyeonrsdy-cloud/gpters-newsletter-assets/main/27/banner-23gi.png
```

## 워크플로우

1. 새 호 시작 → 폴더 생성: `mkdir 28`
2. 이미지 추가 (jpg/png, 이메일용 1280px 권장, 500KB 이하)
3. `git add . && git commit -m "27호 이미지" && git push`
4. 빌드 스크립트가 자동으로 raw URL 박음 (work 레포의 `newsletter/stibee/html_builder.py`)

## 주의

- **반드시 public 레포 유지** — private이면 이메일에서 이미지 안 보임
- **새 호는 새 폴더 사용** (캐시 충돌 방지)
- 이미지 1MB 이하 권장 (이메일 클라이언트 로딩 속도)
- 파일명은 영문 소문자 + 하이픈 (예: `banner-23gi.png`)
