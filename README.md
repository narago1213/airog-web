# 아이로그 소개 사이트 (web)

앱 소개 랜딩 + 개인정보처리방침 + 이용약관. **프레임워크 없는 정적 사이트**(HTML/CSS) — 빌드 과정 없이 폴더만 올리면 됩니다.

```
web/
├── index.html     소개(랜딩) — 히어로 + 기능 + "앱 둘러보기" 갤러리
├── privacy.html   개인정보처리방침
├── terms.html     이용약관
├── styles.css     공용 스타일(앱 디자인 토큰과 동일 계열)
└── screens/       앱 화면 목업(SVG 8종) — 랜딩 갤러리에서 사용
```

## 화면 미리보기(`screens/*.svg`)
랜딩의 폰 목업은 **실제 앱 화면 코드(`src/features/**`)와 디자인 토큰(`src/styles/tokens.ts`)에서 추출한 고충실 SVG 목업**입니다(실기기 캡처가 아님 — 카피·색·레이아웃은 실제 앱과 동일 계열). 각 `390×844` 자기완결 SVG라 외부 리소스가 없고, 그대로 PNG로 내보내면 **앱스토어/플레이스토어 스크린샷**으로도 쓸 수 있습니다. 앱 화면이 크게 바뀌면 해당 SVG도 다시 만들어 교체하세요.

## 로컬에서 보기
```bash
# 그냥 index.html 을 더블클릭해 브라우저로 열어도 됩니다.
# 또는 간단 서버:
cd web && python3 -m http.server 8080   # → http://localhost:8080
```

## 배포 (셋 중 택1 — 무료)
- **Netlify(가장 쉬움)**: https://app.netlify.com/drop 에 `web` 폴더를 **드래그&드롭** → 바로 URL 발급
- **Vercel**: vercel.com → New Project → 이 저장소 연결 → Root Directory 를 `web` 로 지정
- **GitHub Pages**: 저장소 Settings → Pages → 폴더(`/web`) 지정

## 스토어 제출용 URL
배포 후 나온 주소로:
- 개인정보처리방침: `https<your-domain>/privacy.html`
- 이용약관: `https<your-domain>/terms.html`

앱스토어/플레이스토어 등록 시 "개인정보처리방침 URL" 칸에 위 privacy.html 주소를 넣으면 됩니다.

## 주의
- 법무 문구의 **원본(소스 오브 트루스)은 앱의 `src/features/legal/legal-content.ts`** 입니다. 약관/방침을 바꾸면 앱과 이 사이트(privacy.html·terms.html)를 **함께** 수정하세요.
