---
title: "[Cafe24] Cafe24 내용 정리"
date: "2025-09-12"
tags:
    - css
    - javascript
    - html
    - cafe24
    - accordion
    - 배너매니저
    - 파일질라
thumbnail: "/assets/img/thumbnail/cafe24.png"
---
# <span style="color:#616161; font-weight:bold;">Cafe24</span>
mac 기준, cafe24의 onsweb교과서 스킨 기준으로 기록
---

## <span style="color:#ffa59c; font-weight:bold;">import</span>
-주석 안에 " @import(/ons/html/main_bnr.html) " 이러한 형태로 생긴 부분은 해당 파일을 import 한다는 의미이므로, 연결을 끊을 때는 @ 하나만 삭제하시면 됩니다.
(html 파일 연동: @import / css 파일 연동: @css / js파일 연동: @js)-

## <span style="color:#ffa59c; font-weight:bold;">cafe24의 변수 사용</span>
{$aaaa} 형태로 생긴 코드는 카페24 관리자페이지의 설정을 끌어와주는 변수입니다. 
각 모듈마다 지원해주는 변수가 다르기 때문에 모듈과 함께 숙지해주세요.
모듈/변수 리스트는 'https://sdsupport.cafe24.com/product/list.html?cate_no=61' 에서 확인

## <span style="color:#ffa59c; font-weight:bold;">배너매니저 설치 및 사용</span>
-배너의 간편한 관리를 도와주는 앱
-설치방법 : cafe24 - 앱(왼쪽 탭 맨아래 두번째) - 마이앱 - 앱스토어 바로가기 - 배너매니저 설치
-배너 매니저 > 관리하기 > 배너그룹 추가 > 코드명에 코드입력(배너 활성화시 코드명 필요) > 나머지도 입력
-배너 이미지 등 입력
-프로젝트 코드 클릭 하여 코드 복사 > 메인레이아웃 및 공통레이아웃(기본) 배너매니저 코드 수정 > 메인페이지에서 배너 영역 파일열기(main_bnr.html) >
df-banner-code에 이전에 배너그룹추가할 떄 생성한 코드명 입력 (모바일과 PC버전 모두 입력해야나옴)
-배너사이즈는 원본 사이즈로 설정하고 css에서 고쳐야한다.


## <span style="color:#ffa59c; font-weight:bold;">내용 편집</span>
-보통 로고면 로고 모듈, footer면 footer 모듈을 사용하여 만들어 놨기 때문에 디자인 편집에서 마우스를 올리면 편집 버튼이 활성화 됨.
-편집을 누르면 로고는 이미지변경 게시물은 정렬방식 변경 등이 있음
-편집에서 모듈의 html코드도 직접 수정할 수 있음

## <span style="color:#ffa59c; font-weight:bold;">파일질라로 디자인 백업하기</span>
-다운로드할 계정에서 덮어씌울 베이직디자인 생성 후 스킨번호 확인(미리보기)
-디자인 백업 후 스킨번호 확인(미리보기)
-다운로드 받을 계정이 웹FTP인지 디자인FTP인지 확인
-기본 설정에 들어가서 FTP비밀번호변경만 체크해서 변경
-디자인FTP면 권한 신청
-파일질라 실행 후 파일(왼쪽 맨위 아이콘)선택
-항목 선택 - 내사이트 - 새사이트 생성 후 선택
-일반 -> 프로토콜 -> SFTP - SSH File Transfer Protocol 선택
-호스트 : 아이디.ftp.cafe24.com
>디자인 FTP : FTP주소 (ex: ecimg-ftp-c01.cafe24img.com)

-포트 : 웹은 3822
>디자인 FTP : SFTP 접속포트 

-사용자 : 계정 ID
비밀번호 : 기본설정에서 설정한 FTP비밀번호
>디자인 FTP : 권한 신청시 설정한 비밀번호

-연결 
-덮어씌울 디자인 폴더에 백업한 디자인 폴더의 내용 복사 !preference 제외

## <span style="color:#ffa59c; font-weight:bold;">이미지 경로</span>
-대부분의 경우 파일질라에 이미지 업로드하는게 경로가 가장 깔끔함
>ex) cafe24의 이미지 업로드를 사용한 경우 -> /sde_design/skin2/ons/img/f_kakao.svg 
     파일질라에 이미지를 업로드한 경우 -> /ons/img/f_kakao.svg


-웹 FTP인 경우 도메인빼고 상대 경로로 사용
>https://onscorp.cafe24.com/img/003_SKIN.png => /img/003_SKIN.png

-디자인 FTP인 경우 복사한 주소 그대로 사용
>//ecimg.cafe24img.com/pg1455b35414800074/onswebedu/img/default_fixed_mo.png

-스킨 세팅 시 썸네일 이미지 경로 변경 (화질개선)
>웹FTP /file_data/운영자ID/{$real_filename}
디자인FTP //ecimg.cafe24img.com/pg고유넘버/ 운영자ID/file_data{$real_filename}

## <span style="color:#ffa59c; font-weight:bold;">GNB설정</span>
-상품분류 -> 대분류는 상품만 등록할 것
-디자인 편집창 왼쪽 아래에 있는 스마트 디자인 서포트에가면 모든 모듈목록이 있음 게시판 같은 경우 레이아웃/메인에가서 코드 복사해서 GNB에 붙여넣고 다른메뉴의 클래스 동일하게 입혀주기
-메인메뉴 3depth 4depth 보이는 방법은 avigation.js, gnb.js 등  d2를 보이게 하는 스크립트 주석을 풀면 3depth까지 보인다. 

## <span style="color:#ffa59c; font-weight:bold;">게시판 설정</span>

-새로운 형식의 게시판 목록이 필요해서 새폴더에 게시판을 만들었을 경우 경로가 기본경로로될건데 변경할 게시판 고유번호 속성을 갖는 값을 찾아서 경로를 바꾸어주는 스크립트
```javascript
$('.boardListMenu li a[href$="board_no=3"]').attr('href','/board/faq/list.html');
```
-새로 게시판을 추가한 경우 링크가 {$link_board_detail}로 되어있을 경우 /board/benefit/read.html{$param_read} 같은 식으로 변경해주어야한다.
><게시판 경로 설정>
/board/benefit/list.html{$param_list}

/board/benefit/read.html{$param_read}

/board/benefit/modify.html{$param_modify}

/board/benefit/write.html{$param_write}

#### 같은 레이아웃의 게시판을 여러개 만들기
-갤리리 게시판인데 레이아웃으 같은게 여러개 필요할 경우 다른 게시판 번호로된 갤러리게시판을 여러개 만들필요없다
>/board/gallery/list.html?board_no=1002 이렇게 링크를 쓰면 1002(자유게시판) 번호를 갤러리 게시판으로 사용할 수 있다
목록, 취소로 이동하는 링크 변경하는것은 어드민 > 사이트 설정 > 화면경로 설정 > 게시판 설정에서 바꿀 수 있다.

#### 아코디언으로 바꾸기
-게시판 관리에서 게시판 분류를 "상품"으로 바꾸면 "상품 상세페이지내 목록 펼침 여부"와 "본문읽기 설정"이 생김 "접기"와 "리스트 펼치기"로 바꾸고 css로 펼치기 버튼 수정
-기본 게시판 레이아웃과는 다른 아코디언용 list.html을 만들 필요가 있음
-파일 생성 후 자유게시판 목록을 복사해서 만들었다면 free 라는 폴더 경로를 새로만든 폴더 경로로 다 바꾸어주어야함
-클래스명뒤에 1002 같은 보드 고유번호가 붙어있을텐데 그것도 맞는 번호로 다 바꾸어주어야함
-아코디언을 펼칠 이벤트 버튼이 필요할텐데 스마트디자인 서포트 -> 게시판 목록 -> 사용가능한 변수 살펴보다보면 "{$action_content_spread}	내용 펼쳐보기 버튼 이벤트 (상품게시판 전용)" 이걸 onclick에 넣으면 됨

```javascript
    $(document).ready(function() {
    $('.subject.left.txtBreak').on('click', function() {
        $('.faq_accordion_arrow').not($(this).find('.faq_accordion_arrow')).removeClass('rotated');
        $(this).find('.faq_accordion_arrow').toggleClass('rotated');
    });
});
```
>아코디언 화살표 클릭시 회전하기 코드

## <span style="color:#ffa59c; font-weight:bold;">사이드바 고정</span>
-position:sticky 사용, top, left 등 하나이상 기준점을 잡아두면 알아서 부모 높이 안에서 움직인다.
-header가 fixed되어있으면 header높이만큼 (ex)top:100px) 기준점을 잡아주면 된다.

## <span style="color:#ffa59c; font-weight:bold;">결제</span>
-결제 페이지의 은행 선택 칸은 은행과 연동시 자동으로 채워진다.
-틀은 바꾸지 않는 걸 권장하고 디자인은 이미 들어가있는 선택자들을 이용해서 css만 수정하도록 한다.

## <span style="color:#ffa59c; font-weight:bold;">Swiper</span>
-breakpoints는 모바일을 기준으로 잡음 1024면 이하가 아니라 이상을 말하는 것
-슬라이드 사이의 간격은 margin 같은 것 보다 spacebetween을 통해서 잡으면 슬라이드가 밀려나가서 짤리는 걸 방지 할 수 있음 (어차피 margin잡아도 spacebetween이 우선으로 덮어씀)
-css에 ".swiper-wrapper { transition-timing-function: linear !important; }"을 안넣어주면 swiper속성에서 autoSlide에 delay:0 으로 해도 딜레이걸린다.
-슬라이드 이미지 크기가 다를 때 aspect-ratio: 1 / 1.4 속성을 사용하면 비율과 크기를 맞출 수 있다.
-slide 클릭하면 swiper autoplay가 멈추는 현상은 이미지나 슬라이드에 pointer-events: none; 걸어주면 안되고 swiper-wrapper에 걸어줘야한다.

## <span style="color:#ffa59c; font-weight:bold;">배너 높이 꽉채우기</span>
-container에 height: 100%, 그 안에 배너를 담은 그릇에 height: clac(100vh - 헤더높이);, 그리고 배너이미지에 width, height 100%, object-fit:cover; 하면 이쁘게 딱 맞는다.
-풀페이지 배너 꽉채우기
>.ons_mainBanner{box-sizing:border-box; display:flex; justify-content:center; align-items:center; height:100%; align-content:center; flex-wrap:wrap;position: relative; width: 100%; height: 100vh; overflow: hidden; position:relative;}

## <span style="color:#ffa59c; font-weight:bold;">CSS</span>
-.box:not(:last-child) : 마지막 자식요소를 제외하고- , first도 적용 가능
-clamp(최솟값, vw, 최댓값)을 사용하면 크기를 조정할때 vw를 기준으로 가변되고 최솟값보다는 작아지지않고 최댓값보다는 커지지않는다. 반응형에서 미디어쿼리의 양을 줄이기위해 사용하면 좋을 것 같다.
-...으로 말줄임표 표시는 display: block; 일 때만 가능하다.
>text-overflow: ellipsis;는 overflow: hidden; white-space: nowrap;과 width 지정과 세트로 사용

-크롬 버전 137부터 css에서 if문이 사용 가능해졌다. (현재 버전 140) 
```css
padding: if(media(max-height: 1200px) :  0; else: 0 40px);
``` 
>높이 1200px 이하에서는 패딩을 0으로하고 그 밖에는 가로 양쪽 40px을 추가한다.
관련 블로그 : https://sorto.me/docs/Web/CSS/Functions/if

## <span style="color:#ffa59c; font-weight:bold;">스킨 설치</span>
-스킨 백업 > 기본스킨에 업로드 > 배너매니저 세팅 > 상품 정보 표시 설정 세팅 (메인진열 세팅) > 하위메뉴 노출 확인 및 분류리스트 사용함 유무 > 게시판 및 썸네일, 이미지 경로 변경 > 엑박이미지(png 등) 넣어주기 > 상품 썸네일 크기 설정 모두 1000 

-스킨 썸네일 다운로드 : 구글시트 - 온스계정 - 카페24 디자인센터 관리자페이지 (파트너) 사이트 로그인 -Designs - 쇼핑몰 디자인 - 스킨 선택 - 이미지 다운로드
-사용자가 변경할 수 있을 것 같은건 안해도되고 개발자가 해야될 것 같은 것이나 어려운 것만 세팅
-이미지경로, 썸네일 등 웹FTP인 경우 아래와 같이 경로 수정해야함
```html
<img s c="/file_data/계정 아이디/{$real_filename}" alt="" onerror="this.src='{$image_small_src}'"/>
```
-디자인FTP인 경우 : //ecimg.cafe24img.com/pg고유넘버/운영자ID/file_data{$real_filename}
>pg고유넘버 : pg고유넘버는 사이트마다 하나씩 정해져있으며 이미들어가있는 이미지를 (ex)로고) 개발자모드로보면 pg번호가 써있는 것이 있다.

## <span style="color:#ffa59c; font-weight:bold;">javascript</span>
-뒤에 붙일 때는 append를 사용하고 앞에 붙일 때는 before보다는 prepend를 사용 before은 화면을 줄였다 늘리면 여러개 붙는 버그가 있음
>before은 태그 밖의 앞에 붙이지만 prepend와 append는 태그 안에서 앞뒤에 붙인다. 아래 코드 처럼하면 태그 밖에 붙일 수 있다

```javascript
salePriceEl.parent().prepend(sSaleText);
```

-자바스크립트로 로드 후 붙는 글자 없애기. 없어질때까지 반복 후 멈추기
```javascript
적립금 자바스크립트로 “원” 

window.onload = function () {
    let mileage = document.querySelector(".mypage_mileage");

    let interval = setInterval(() => {
        if (mileage && mileage.textContent.includes("원")) {
            mileage.textContent = mileage.textContent.replace(/원/g, "");
            clearInterval(interval); // 더 이상 반복 안 하도록 중단
        }
    }, 1); // 0.001초 간격으로 검사
};
```

## <span style="color:#ffa59c; font-weight:bold;">깔끔한 한줄에 콘텐츠 4개씩 배치</span>
-상품을 4개씩 진열해야할 때, 사이 간격을 넣으면 flex-wrap 때문에 밑으로 넘어갈 때, 25%씩하면 넘어가고 23%하면 반응형크기마다 끝에 살짝 공간이 남을 때
-25% 너비에 간격 24px을 뺀 크기만큼 영역을 차지하게해서 깔끔하게 진열
```css
.prdList { display: flex; flex-wrap: wrap; gap: 24px; list-style: none; padding: 0; margin: 0; }
.prdList li { flex: 0 calc(25% - 24px); box-sizing: border-box; }
```
>오른쪽 여백 생길거임 gap만큼 다른거에도 마진 gap만큼 주던지

## <span style="color:#ffa59c; font-weight:bold;">깔끔한 반응형 콘텐츠 너비 지정</span>
```css
.product_top_container, 
.product_container {
  overflow: hidden;
  box-sizing: border-box;
  max-width: calc(100% - clamp(270px, 26.4583vw ,508px)); /* 좌우 270px씩 여백 확보 */
  margin: 0 auto; /* 중앙 정렬 */
  padding: 0 16px;
}
```

## <span style="color:#ffa59c; font-weight:bold;">보안 문자</span>
-비로그인시 게시판 작성할 때 개인정보 제 3자 동의 항목을 키면 보안문자가 나온다. 게시판 설정에서 스팸 자동생성방지 기능을 체크해제하면 사라진다.

## <span style="color:#ffa59c; font-weight:bold;">배경이 부모 패딩을 넘어서 꽉채우기</span>
-pc에서는 배경이 패딩안쪽으로 존재하는데 모바일에서는 배경이 부모 패딩을 넘어서 꽉채우는 경우가 종종 있다.
> .배경 { position: relative; left: 50%; width: 100vw; transform: translateX(-50%); }

## <span style="color:#ffa59c; font-weight:bold;">스냅위젯</span>
-인스타그램 게시물을 하단에 딱 붙여야할 때 높이외에 여백이 조금 붙는 경우가 있는데 font-size:0; 해주면 사라진다.

## <span style="color:#ffa59c; font-weight:bold;">문의하기 등 제출시 구글시트와 이메일 전송 방법</span>
-https://docs.google.com/spreadsheets/d/1Bn4m6iA_Xch1zzhNvo_6CoQWqOAgwwkOWJKC-phHx2Q/copy
-구글계정 로그인 후 위 링크로가서 사본생성 > 확장프로그램 > Apps Script > 8번째 줄 주석 풀고 이메일 입력(이메일 전송 희망시) > 101 번줄
 var row = [Utilities.formatDate(new Date(), 'GMT+9', 'yyyy-MM-dd HH:mm:ss')]; // format date in KST (GMT+9) 한글 시간으로 포맷 > 우측 상단 배포 > 새배포 > 나에게로 인증, 모든사용자로 설정 후 액세스 승인 > 웹 url 복사 > form action 에 url 추가
```html
<div class="container contact_right">
            <form id="emailForm" class="gform" method="POST" data-email="easypeasy2787@gmail.com"
                action="https://script.google.com/macros/s/AKfycbxQBtkIurBJlbqZSBA4zw-nSGSSqiGEpUsB1-bSohmjYqJdL6hGL1qSHLuFCkkJHfsyWg/exec">
                <div class="form_group">
                    <input type="text" class="form-control" id="company" name="회사명" placeholder="브랜드명(회사명)" required ><>
                </div>
                <div class="form_group">
                    <input type="text" class="form-control" id="name" name="담당자" placeholder="담당자명" required><>
                </div>
                <div class="form_group">
                    <input type="tel" class="form-control" id="phone" name="연락처" placeholder="연락처" required><>
                </div>
                <div class="form_group">
                    <input type="text" class="form-control" id="email" name="이메일" placeholder="이메일" required><>
                </div>
                <div class="form_group">
                    <textarea type="text" class="form-control" id="content" name="문의내용" placeholder="문의내용" required></textarea>
                </div>
                <div class="check"><input type="checkbox" id="checkbox" required><label for="checkbox" class="check">개인정보 수집 및 이용에 동의합니다.</label></div>
                <div class="btm">
                    <button id="btnSubmit" class="btn-submit">문의하기</button>
                </div>
            </form>
        </div>       
```
```javascript
(function() {
    // get all data in form and return object
    function getFormData(form) {
    var elements = form.elements; // 폼 내 모든 요소를 가져옴
    var honeypot; // 봇 방지 필드

    var fields = Object.keys(elements).filter(function(k) {
        if (elements[k].name === "honeypot") {
            honeypot = elements[k].value;
            return false;
        }
        return true;
    }).map(function(k) {
        if (elements[k].name !== undefined) {
            return elements[k].name;
        } else if (elements[k].length > 0) {
            return elements[k].item(0).name;
        }
    }).filter(function(item, pos, self) {
        return self.indexOf(item) == pos && item;
    });

    var formData = {};
    fields.forEach(function(name) {
        var element = elements[name];
        
        if (element.length) { // 요소가 배열인 경우 (예: 라디오 버튼)
            var data = [];
            for (var i = 0; i < element.length; i++) {
                var item = element.item(i);
                if (item.checked || item.selected) {
                    data.push(item.value);
                }
            }
            formData[name] = data.join(', ');
        } else {
            formData[name] = element.value; // 일반 요소인 경우 값 할당
        }

    });

    formData.formDataNameOrder = JSON.stringify(fields);
    formData.formGoogleSheetName = form.dataset.sheet || "responses"; // default sheet name
    formData.formGoogleSendEmail = form.dataset.email || ""; // no email by default

    return { data: formData, honeypot: honeypot };
}

    function handleFormSubmit(event) {
    event.preventDefault();
    var form = event.target;
    var formData = getFormData(form);
    var data = formData.data;

    if (formData.honeypot) {
        return false;
    }

    // Show loading spinner and message
    var loadingSpinner = document.querySelector(".loading-spinner");
    if (loadingSpinner) {
        loadingSpinner.style.display = "block";
    }

    // Disable submit button and change its text
    var submitButton = form.querySelector("button[type='submit']");
    if (submitButton) {
        submitButton.disabled = true;
        submitButton.textContent = "처리 중...";
    }

    var url = form.action;
    var xhr = new XMLHttpRequest();
    xhr.open('POST', url);
    xhr.setRequestHeader("Content-Type", "application/x-www-form-urlencoded");

    xhr.onreadystatechange = function() {
        if (xhr.readyState === 4) {
            // Hide loading spinner
            if (loadingSpinner) {
                loadingSpinner.style.display = "none";
            }

            if (xhr.status === 200) {
				form.reset();
                alert("문의가 완료되었습니다.")
            } else {
                // Handle error condition
                alert("연결 상태를 확인 후 다시 시도해 주세요.");
            }
        }
    };

    var encoded = Object.keys(data).map(function(k) {
        return encodeURIComponent(k) + "=" + encodeURIComponent(data[k]);
    }).join('&');

    xhr.send(encoded);
}

    function loaded() {
        var forms = document.querySelectorAll("form.gform");
        for (var i = 0; i < forms.length; i++) {
            forms[i].addEventListener("submit", handleFormSubmit, false);
        }
    }
    document.addEventListener("DOMContentLoaded", loaded, false);
})();
```

## <span style="color:#ffa59c; font-weight:bold;">TIP</span>
-문자열찾기가 현재화면에서밖에 못찾아서 vscode로 옮겨서 검색하던지 스크롤하면서 문자열찾기를 계속 눌러봐야함 (불편)
-소비자가 : 원가, 판매가 : 할인 등 적용한 정가
-할인판매가 할인율 보이게하기 : 쇼핑몰설정 -> 상품 설정 -> 추가 설정 -> 팔인판매가 사용함, 표시문구 "[:DISCOUNT_PERCENT:]"(소비자가와 판매자가의 가격을 설정하면 알아서 계산됨)
>표시문구 변수 ex)
[:DISCOUNT_AMOUNT:] 할인 금액 표시
[:DISCOINT_PERCENT:] 할인율(%) 표시
[:MEMBER_GRADE] 접속한 회원의 등급명 표시

-편집창 왼쪽 아래 스마트 디자인 서포트 모듈 목록 및 코드 활용하기
-클래스 우선순위가 밀리면 덮어씌워진 클래스명에 하나를 더 추가해서 우선순위를 높이자(클래스 중첩 갯수가 많아지면 우선순위 점수가 높아짐)
-무한스크롤 구현 (스크롤시 마지막 게시물이 나올 때 까지 생겨남) 한번에 모든 게시물을 불러오고 초기 9개만 표시 후 스크롤이 맨 아래에 도착할 시 반복문으로 9개씩 추가적으로 보여지게 구현 페이지별 url이 다르다면 스크롤이 맨 아래로 갈 시 1페이지 밑에 2페이지를 붙여서 불러오는 식으로 구현도 가능



## <span style="color:#ffa59c; font-weight:bold;">오류 수정</span>
-js파일에서 파일질라에 업로드한 이미지 불러오는 오류(유지보수에 안좋아서 수정)
-mouseover/mouseout 대신 mouseenter/mouseleave 사용 (child 요소에 이벤트 중첩되는 오류 개선)
-예전작업된 jQuery에서 on메서드가 작동하지 않을 시 버전 확인. 1.4.4 이하에서는 .on대신 .live사용해야함


## <span style="color:#ffa59c; font-weight:bold;">워드프레스 기능 뺀 미리보기용 사이트 만들기</span>
1.simply static 플러그인 다운로드
2.setting - general 에서 Relative Path와 바로아래 PATH 입력 : https://jinsu1.github.io/demo1 
3.셋팅 맨아래 Exclude에 아래 내용 넣고 저장
```
/wp-admin
/wp-login.php
/wp-json
/xmlrpc.php
```
4.Generate 눌러서 zip파일 저장
5.vscode로 열어서 라이브 서버 확인해보고 github 레포에 업로드
6.깃허브 페이지 제작 후 접속. 깨진다면 경로문제!

## <span style="color:#ffa59c; font-weight:bold;">git push ssh로 계정 변경</span>
-ssh-keygen -t ed25519 -C "onsweb.shopify@gmail.com" : ssh 키 생성
-cat ~/.ssh/id_ed25519.pub : 공개키 복사
-github 에 ssh and GPG jeys > New SSH key 에 붙여넣기
-git remote add origin git@github.com:onsshopi/broommasterclean.git : 원격 저장소 변경
-푸쉬 진행