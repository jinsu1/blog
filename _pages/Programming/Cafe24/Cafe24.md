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

## <span style="color:#ffa59c; font-weight:bold;">TIP</span>
-문자열찾기가 현재화면에서밖에 못찾아서 vscode로 옮겨서 검색하던지 스크롤하면서 문자열찾기를 계속 눌러봐야함 (불편)
-소비자가 : 원가, 판매가 : 할인 등 적용한 정가
-할인판매가 할인율 보이게하기 : 쇼핑몰설정 -> 상품 설정 -> 추가 설정 -> 팔인판매가 사용함, 표시문구 "[:DISCOUNT_PERCENT:]"(소비자가와 판매자가의 가격을 설정하면 알아서 계산됨)
>표시문구 변수 ex)
[:DISCOUNT_AMOUNT:] 할인 금액 표시
[:DISCOINT_PERCENT:] 할인율(%) 표시
[:MEMBER_GRADE] 접속한 회원의 등급명 표시


## <span style="color:#ffa59c; font-weight:bold;">오류 수정</span>
-js파일에서 파일질라에 업로드한 이미지 불러오는 오류(유지보수에 안좋아서 수정)
-mouseover/mouseout 대신 mouseenter/mouseleave 사용 (child 요소에 이벤트 중첩되는 오류 개선)
-예전작업된 jQuery에서 on메서드가 작동하지 않을 시 버전 확인. 1.4.4 이하에서는 .on대신 .live사용해야함

