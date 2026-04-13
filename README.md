# EXEM 온보딩 DAY2 웹 프레젠테이션

신규입사자 온보딩 2일차 교육자료를 웹 프레젠테이션으로 변환한 프로젝트입니다.

## 배포 URL

https://onboarding-day2-sand.vercel.app

## 구성

| 탭 | 내용 | 슬라이드 |
|----|------|----------|
| 탭1 | 제품 프리뷰 교육 | p1 ~ p18 |
| 탭2 | 핵심가치 워크샵 | v1 ~ v46 |

## 구조

```
onboarding-day2/
├── index.html                    # 전체 프레젠테이션 (HTML + CSS + JS)
├── media/                        # 이미지, 영상 파일
│   ├── exem_logo_*.png           # EXEM 로고
│   ├── image*.jpeg/png/jpg/svg   # 슬라이드 이미지
│   ├── media1.mp4                # 스톡데일 패러독스 영상
│   ├── nvidia2.mp4               # 젠슨 황 영상 (재편집본)
│   └── logo_*.png                # 솔루션 로고
├── 신규입사자 온보딩_DAY2.pptx   # 원본 PPT (참고용)
└── README.md
```

## 주요 기능

- **웹 프레젠테이션**: 브라우저에서 바로 사용, 좌우 화살표/스와이프로 슬라이드 전환
- **발표자 모드**: `P`키로 토글, 별도 팝업에 발표 스크립트 표시
- **인터랙티브 요소**: 30 Circles 타이머, 클릭 토글 퀴즈, 시어핀스키 피라미드 등
- **반응형**: 모바일/태블릿 대응

## 수정 방법

### 슬라이드 내용 수정

`index.html` 내에서 해당 슬라이드 ID를 찾아 수정합니다.

- 탭1 슬라이드: `id="p1"` ~ `id="p18"`
- 탭2 슬라이드: `id="v1"` ~ `id="v46"`

```html
<!-- 예: v18 열정 슬라이드 -->
<div id="v18" class="s s-dark">
  <!-- 이 안의 텍스트/이미지를 수정 -->
</div>
```

### 이미지 교체

1. `media/` 폴더에 새 이미지 추가
2. `index.html`에서 해당 이미지 경로 변경

### 발표자 스크립트 수정

`index.html` 하단의 `presenterScripts` 객체에서 수정합니다.

```javascript
const presenterScripts = {
  "p1": { title: "슬라이드 제목", time: "2분", script: "발표 스크립트..." },
  // ...
};
```

### 핵심가치 내용 변경

핵심가치가 변경되면 탭2(v1~v46) 슬라이드의 텍스트를 직접 수정합니다. 현재 EXEM 6대 핵심가치 기준:
- 열정 (Passion)
- 신속 (Speed)
- 몰입 (Flow)
- 성취/책임 (Professional)
- 협력/수용 (Partnership)
- 투명/진정성 (Communication)

## 배포

```bash
# Vercel로 배포
npx vercel --prod --yes
```

## 디자인 시스템

- 폰트: Pretendard Variable (CDN)
- 메인 색상: EXEM Blue `#2D79DB`, Cyan `#50EDFF`
- 배경: `#F8F9F9`
- border-radius: 8px (기본), 12px (대형)

## 기술 스택

- 순수 HTML/CSS/JS (프레임워크 없음)
- 단일 파일 (`index.html`)
- Vercel 배포
