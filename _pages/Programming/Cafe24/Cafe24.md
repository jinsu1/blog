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
-사용 : 프로젝트 코드 - '기본' 스크립트 코드 복사 - 디자인편집 - 기존 배너매니저 스크립트 교체 (main.html, layout.html)

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



### 실행결과
![result](/blog/assets/img/posting/array2.PNG)