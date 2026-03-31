---
title: "[Claude] Claude 코딩"
date: "2026-03-31"
tags:
    - css
    - javascript
    - html
    - Claude
    - AI
thumbnail: "/assets/img/thumbnail/claude.jpg"
---
# <span style="color:#616161; font-weight:bold;">Claude</span>
claude & 피그마 MCP연결을 통한 AI 개발
---

## <span style="color:#ffa59c; font-weight:bold;">Setting</span>
-vscode 플러그인 Claude Code for VS code 설치
-피그마(dev모드 변경이 가능한 유료결제 계정) > 홈 > 왼쪽 상단 프로필 > 셋팅 > 보안 > 토큰 생성 > vscode의 claude 채팅에 토큰에 mcp 연결해달라고 요청>
피그마 영역 선택 후 url 복사 > node-id 알려주고 클로드에게 인식 요청 > 완료

-톡 투 피그마 플러그인 : 아직 연결에 성공해보지는 못했지만 무료계정 사용가능하다고함
>설치위치 https://www.figma.com/community/plugin/1485687494525374295/talk-to-figma-mcp-plugin


## <span style="color:#ffa59c; font-weight:bold;">클로드 개발명령</span>
-페이지 전체를 한번에 개발 요청하면 시안을 제대로 인식하지 못하므로 한 페이지의 영역별로 나누어서 개발 명령 필요
-이미지 병합을해도 클로드는 별개로 인식하므로 이미지 병합 > 추출 > 재업로드 하여 사용 ex)메인배너

## <span style="color:#ffa59c; font-weight:bold;">2026/3/31 업데이트 클로드 개발 프롬프트</span>
```

Figma MCP 데이터를 1px 오차 없이 HTML/CSS/JS로 변환해줘

[작업 대상]

node-id=154-1802

[데이터 소스]

반드시 MCP에서 제공된 디자인 데이터만 사용
임의 해석, 추측, 창의적 수정 절대 금지

[출력 요구사항]

단일 HTML 파일 형태로 출력

JS가 필요한 경우 태그로 하단에 포함
불필요한 설명 없이 코드만 출력

[레이아웃 규칙]

-전체 레이아웃은 flexbox 기반으로 구성
-MCP의 auto-layout → flex로 정확히 변환
-direction, align, justify, gap 값 정확히 반영
-absolute는 꼭 필요할때만 사용
-section 콘텐츠 넓이 확인하여 max-width 설정 ex) max-width:1280px; 등

[스타일 정확도 규칙]
다음 속성은 MCP 값을 100% 그대로 반영:

-font-family
-font-size
-font-weight
-line-height
-letter-spacing
-color (rgba 포함)
-background-color / gradient
-padding (4방향 정확하게 오차없이 사용)
-margin (4방향 정확하게 오차없이 사용)
-border-radius
-border (두께/색상)
-width / height 는 calc와 %, aspect-ratio를 사용해 반응형으로 사용
-gap (auto-layout 기준)
-shadow (있을 경우)

[정렬 규칙]

text-align, vertical alignment 모두 MCP 기준 그대로
center 정렬 여부 임의 판단 금지
모든 요소는 Figma 기준 좌표/정렬 유지

[이미지 처리 규칙]

MCP에 이미지 URL이 없을 경우:
-회색 박스 (#E5E5E5)로 대체

[클래스 네이밍 규칙]

모든 클래스는 "mysite-" prefix 사용
예: mysite-hero, mysite-hero-title, mysite-hero-button
절대 generic 클래스 사용 금지 (container, wrapper 등 금지)

[반응형]

-모바일 시안과 PC시안을 모두 확인하여 개발
-모바일은 화면넓이 1024px이하\
-테블릿은 별도로 없고 모바일과 통합


[계층 구조 규칙]

MCP의 레이어 구조를 그대로 HTML 계층으로 반영
불필요한 div 추가 금지
wrapper 남발 금지

[텍스트 규칙]

줄바꿈()은 MCP에 명시된 경우만 사용
텍스트 내용 절대 수정 금지

[인터랙션]

hover, 클릭 효과는 MCP에 정의된 경우만 구현
없으면 추가 금지

[검증 기준]
아래 항목을 모두 만족해야 한다:

Figma와 시각적으로 동일
spacing 오차 0px
패딩/마진 완전 일치
폰트/컬러 완전 일치
DOM 구조가 MCP와 동일

[출력 형식]

코드 외 텍스트 절대 포함 금지
HTML → CSS → JS 순서 유지

이제 MCP 데이터를 기반으로 코드 생성해줘
```