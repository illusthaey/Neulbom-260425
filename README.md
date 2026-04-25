# 늘봄학교 실무 가이드

늘봄 관련 내용만 분리한 새 도메인용 정적 사이트입니다.

## 핵심 변경사항

- 상단 사이트 제목, 로고 문구, 주요 메뉴, 페이지별 상단 문구, 페이지 목차, 푸터 문구를 `static/site-config.js`로 분리했습니다.
- 개별 HTML은 `data-page-key`만 지정하고, 공통 헤더·상단 히어로·목차·푸터는 `static/site.js`가 자동 렌더링합니다.
- 모든 페이지에 공통 “위로” 버튼을 추가했습니다.
- 기존 문구는 최대한 유지했습니다.

## 주요 페이지

- `/` : 메인
- `/study-method/` : 업무 공부하는 방법
- `/training-proposal/` : 늘봄지원실장 및 늘봄학교전담사 역량 강화 연수 제안서
- `/admin-accounting-guide/` : 늘봄 업무 처리 시 필요한 행정·회계 업무 가이드
- `/references/` : 근거자료
- `/file-download/docs/` : PDF 자료 다운로드

## 공통 문구 수정 방법

사이트 제목, 카테고리, 상단 메뉴명, 페이지별 상단 문구를 바꾸려면 다음 파일만 수정하면 됩니다.

```text
static/site-config.js
```

예를 들어 메뉴명을 바꾸려면 `navigation` 배열의 `label`을 수정하고, 페이지 상단 제목·설명·목차를 바꾸려면 `pages` 객체의 해당 `pageKey` 항목을 수정합니다.

각 HTML의 `body`에는 다음처럼 페이지 키만 유지하면 됩니다.

```html
<body data-page-key="study-method">
```

## 배포

정적 HTML/CSS/JS만 사용합니다. GitHub Pages, Cloudflare Pages, Netlify, 일반 웹호스팅에 업로드할 수 있습니다.

새 도메인 연결 시 `CNAME.example`을 참고하여 실제 도메인을 `CNAME`에 입력하고, 필요 시 `sitemap.xml.example`의 도메인을 교체하세요.
