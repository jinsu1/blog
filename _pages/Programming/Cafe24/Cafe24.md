---
title: "[Cafe24] 기본내용 다루기"
date: "2025-09-12"
thumbnail: "/assets/img/thumbnail/cafe24.png"
---
# <span style="color:#616161; font-weight:bold;">Cafe24</span>
mac 기준, cafe24의 onsweb교과서 스킨 기준으로 기록
---

## <span style="color:#ffa59c; font-weight:bold;">import</span>
-주석 안에 " @import(/ons/html/main_bnr.html) " 이러한 형태로 생긴 부분은 해당 파일을 import 한다는 의미이므로, 연결을 끊을 때는 @ 하나만 삭제하시면 됩니다.
(html 파일 연동: @import / css 파일 연동: @css / js파일 연동: @js)

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


## <span style="color:#ffa59c; font-weight:bold;">내용 편집</span>
-보통 로고면 로고 모듈, footer면 footer 모듈을 사용하여 만들어 놨기 때문에 디자인 편집에서 마우스를 올리면 편집 버튼이 활성화 됨.
-편집을 누르면 로고는 이미지변경 게시물은 정렬방식 변경 등이 있음
-편집에서 모듈의 html코드도 직접 수정할 수 있음

## <span style="color:#ffa59c; font-weight:bold;">파일질라로 디자인 백업하기</span>
-다운로드할 계정에서 덮어씌울 베이직디자인 생성 후 스킨번호 확인(미리보기)
-디자인 백업 후 스킨번호 확인(미리보기)
-다운로드 받을 계정이 웹FTP인지 디자인FTP인지 확인
-디자인FTP면 권한 신청
-기본 설정에 들어가서 FTP비밀번호변경만 체크해서 변경
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

## <span style="color:#ffa59c; font-weight:bold;">GNB설정</span>
-상품분류 -> 대분류는 상품만 등록할 것
-디자인 편집창 왼쪽 아래에 있는 스마트 디자인 서포트에가면 모든 모듈목록이 있음 게시판 같은 경우 레이아웃/메인에가서 코드 복사해서 GNB에 붙여넣고 다른메뉴의 클래스 동일하게 입혀주기

## <span style="color:#ffa59c; font-weight:bold;">게시판 설정</span>

-새로운 형식의 게시판 목록이 필요해서 새폴더에 게시판을 만들었을 경우 경로가 기본경로로될건데 변경할 게시판 고유번호 속성을 갖는 값을 찾아서 경로를 바꾸어주는 스크립트
```javascript
$('.boardListMenu li a[href$="board_no=3"]').attr('href','/board/faq/list.html');
```

#### 아코디언으로 바꾸기
-게시판 관리에서 게시판 분류를 "상품"으로 바꾸면 "상품 상세페이지내 목록 펼침 여부"와 "본문읽기 설정"이 생김 "접기"와 "리스트 펼치기"로 바꾸고 css로 펼치기 버튼 수정
-기본 게시판 레이아웃과는 다른 아코디언용 list.html을 만들 필요가 있음
-파일 생성 후 자유게시판 목록을 복사해서 만들었다면 free 라는 폴더 경로를 새로만든 폴더 경로로 다 바꾸어주어야함
-클래스명뒤에 1002 같은 보드 고유번호가 붙어있을텐데 그것도 맞는 번호로 다 바꾸어주어야함
-아코디언을 펼칠 이벤트 버튼이 필요할텐데 스마트디자인 서포트 -> 게시판 목록 -> 사용가능한 변수 살펴보다보면 "{$action_content_spread}	내용 펼쳐보기 버튼 이벤트 (상품게시판 전용)" 이걸 넣으면 됨

## <span style="color:#ffa59c; font-weight:bold;">사이드바 고정</span>
-position:sticky 사용, top, left 등 하나이상 기준 점을 잡아두면 알아서 부모 높이 안에서 움직인다.
-header가 fixed되어있으면 header높이만큼 (ex)top:100px) 기준점을 잡아주면 된다.


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


## <span style="color:#ffa59c; font-weight:bold;">오류 수정</span>
-js파일에서 파일질라에 업로드한 이미지 불러오는 오류(유지보수에 안좋아서 수정)
-mouseover/mouseout 대신 mouseenter/mouseleave 사용 (child 요소에 이벤트 중첩되는 오류 개선)
-예전작업된 jQuery에서 on메서드가 작동하지 않을 시 버전 확인. 1.4.4 이하에서는 .on대신 .live사용해야함

