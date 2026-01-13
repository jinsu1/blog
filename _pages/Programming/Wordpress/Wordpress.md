---
title: "[Wordpress] Wordpress 내용 정리"
date: "2025-12-23"
tags:
    - css
    - javascript
    - html
    - wordpress
    - cafe24
    - homepage
    - solution
thumbnail: "/assets/img/thumbnail/Wordpress_logo.png"
---
# <span style="color:#616161; font-weight:bold;">Wordpress</span>
-wordpress.com과 wordpress.org는 뿌리는 같지만 다른 솔루션으로 대부분의 워드프레스는 .org로 제작된다.
카페24 호스팅센터에서 뉴매니지드 워드프레스 상품으로 호스팅과 워드프레스.org를 묶음으로 판매하는 상품 기준으로 작업
---

## <span style="color:#ffa59c; font-weight:bold;">세팅</span>
1.상품을 결제하면 워드프레스 상품은 자동으로 워드프레스가 설치된다.
2.자신의 도메인주소에 /wp-admin을 입력하면 어드민페이지로 이동된다.
3.결제할때 설정한 어드민 비밀번호를 입력해서 어드민페이지로 로그인한다.
4.설정 > 사이트 제목 입력 > 시간대 : 서울 
5.모양 > 테마 > 원하는 테마 추가
6.플러그인 > 플러그인 일괄 업데이트 > 플러그인 추가 > 엘리멘터 설치 후 활성화
7.페이지 > 모든 페이지 > 기본 페이지들 일괄동작:휴지통으로 이동 

*사이트 속도향상을 위해 안쓰는 테마, 글, 페이지 등 기본으로 깔려있는 것 삭제 


## <span style="color:#ffa59c; font-weight:bold;">GNB구성(header, footer)</span>
1.워드프레스는 페이지가 있어야 GNB를 설정할 수 있기때문에 페이지부터 다 만들어야한다.
3.메뉴 생성이 대메뉴는 설정할 것이고 페이지 추가는 서브메뉴들만 추가하면 된다.
2.페이지 추가 > 페이지 설정(왼쪽 상단) > 페이지 제목 입력 > 상태 : 발행됨 (임시글 상태 제거) > 페이지 전체 너비 : Elementer전체너비 > 공개 > 같은 형식으로 모든 페이지 추가
3.모양 > 메뉴 > 메뉴이름 : 상단메뉴 > 메뉴 저장 > 하위메뉴 하나 선택하여 메뉴에추가 > 이름 대메뉴이름으로 변경 > 하위메뉴로 추가할 메뉴 모두 선택하여 메뉴에 추가 > 원하는 대메뉴 밑으로 한칸 옆으로 드래그하여 추가 
4.아래 메뉴를 수정하거나, 새 메뉴 만들기를 하세요. 변경사항 저장을 잊지 마세요! 라는 문구의 새 메뉴 만들기 클릭 > 메뉴이름 : 하단메뉴 > 상단과 마찬가지로 생성
5.페이지 추가 > index페이지 생성  > 로고 클릭 > 사이트 설정 > 전역 색상 > 기본, 보조, 텍스트, 포인트(악센트) 컬러 지정, 전역 글꼴 > 글꼴 및 각 폰트 굵기 등 설정
6.사이트 설정 > 레이아웃 > 콘텐츠 너비 설정(1280px 등) > 간격 0 > 기본 페이지 레이아웃: Elementer전체 넓이
7.메뉴 설정 > 상단 메뉴 > 주메뉴, 보조매뉴, 캔버스 외부메뉴, 로그인한 계정 메뉴 체크 후 메뉴 저장, 하단메뉴 > 푸터 메뉴 체크 후 저장

## <span style="color:#ffa59c; font-weight:bold;">Header(헤더)</span>
1.모양 > 사용자 정의 > 사이트 제목 및 로고 > 로고 등록, 로고 폭 조정 > 사이트 제목 삭제 또는 사이트 제목 가시성 PC, Teblet, Mobile 모두 해제하여 가리기 
2.주메뉴 > 서브메뉴(펼쳐짐) 폭 변경 > 아이템 디바이더(서브메뉴에 밑줄) 추가 여부 > 상단 탭의 DESIGN 
> 메뉴 호버 스타일 지정, 상단 오프셋 지정(하위메뉴와 대메뉴사이의 간격), 하위 메뉴 애니메이션 지정, border-radius 지정, 테두리 지정, 메뉴 색상 순서대로 기본, 오버 색상, 액티브 색상
3.아스트라 경우 헤더 고정이 유료이다. 무료로 사용하려면 Sticky Menu & Sticky Header 플러그인을 다운받으면 쉽게 할 수 있다.
4.설치 후 왼쪽 탭메뉴 설정에 sticky menu라는 서브메뉴가 생긴다. Sticky Element: (required) 여기에 헤더의 아이디나 클래스를 입력해주면 끝이다.
>-아스트라의 경우 ".site-header"를 입력하면 된다. 그 외에도 고정메뉴와 상단 거리 조정, 관리자 툴바 가리는 문제 해결, 정해진 픽셀 이하, 이상에서 고정해제 등 옵션이 있다.
5.WP Mega Menu 메가 메뉴 플러그인

-상단 투명 헤더 코드(아스트라)

```css
/* 메인페이지에서만 헤더 투명 */
body.home .site-header {
    position: fixed;
    width: 100%;
    background: transparent;
    transition: background-color 0.3s ease, box-shadow 0.3s ease;
    z-index: 999;
}

body.home .ast-primary-header-bar {background-color:transparent;}
body.home .main-header-bar,
body.home .ast-above-header-bar {border:none;}

/* 스크롤 시 헤더 스타일 */
body.home .site-header.scrolled {
    background-color: #ffffff;
    box-shadow: 0 2px 10px rgba(0,0,0,0.08);
}

/* 관리자바 있을 때 보정 */
.admin-bar body.home .site-header {
    top: 32px;
}
```
-WP Headers and Footers 플러그인의 Script in Footer에 추가
```js
<script>
document.addEventListener('DOMContentLoaded', function () {
    if (!document.body.classList.contains('home')) return;

    const header = document.querySelector('.site-header');
    if (!header) return;

    window.addEventListener('scroll', function () {
        if (window.scrollY > 50) {
            header.classList.add('scrolled');
        } else {
            header.classList.remove('scrolled');
        }
    });
});
</script>
```

## <span style="color:#ffa59c; font-weight:bold;">Footer(푸터)</span>
1.푸터는 기본으로 Copyright만 있는데 컨텐츠 하단 Copyright옆 여백을 클릭하면 엘리먼트 삽입 창이 뜬다. footer menu 클릭하여 추가
2.추가된 콘텐츠 박스를 드래그하여 순서를 바꿀 수 있다.
3.인라인(가로), 세로배열, 정렬방식, 디자인에서 색상 및 크기, 간격을 각 반응형에 맞춰 설정한다.
4.컨텐츠 화면에서 footer에 마우스를 가져가서 연필모양의 편집을 선택한다.
5.기둥은 푸터를 몇등분으로 나눌 것인지 선택하는 메뉴이다
6.디자인 설정에서 색상 및 여백을 설정한다.
7.general로 돌아와서 내부 요소 레이아웃 : row, column 정렬 선택, 폭은 레이아웃 1280px, 또는 전체폭 선택, 높이는 푸터의 전체 높이, 정렬을 선택한다.

## <span style="color:#ffa59c; font-weight:bold;">배너</span>
1.수정할 페이지로 접속하여 엘리멘터 편집기를 연다.
2.배너 같은 경우 위젯 + 버튼을 클릭하여 플렉스박스, 원하는 형태를 선택한다.
3.왼쪽 상단 위 요소 추가 + 버튼을 클릭하여 타이틀, 텍스트 박스 등을 넣는다.
4.타이틀 줄넘김은 <br />이고 텍스트 박스의 줄넘김은 enter는 문단 넘기기, shift+enter는 줄바꿈이다.
5.배너 영역을 오른쪽 클릭하고 컨테이너 편집을 클릭, 스타일 > 배경유형 > 슬라이드쇼 선택, 이미지추가 클릭 후 슬라이드할 이미지들을 드래그해서 넣고 갤러리 삽입을 한다.
6.이미지 삽입 후 하단에서 무한 루프, 딜레이, 애니메이션 크기 등 슬라이드 설정을 할 수 있다. 배경크기 : 덮기는 object-fit:cover; 와 같은 역할이고 위치 정중앙으로하면 된다.
7.Ken Burns효과는 이미지를 서서히 확대,축소 시키는 애니메이션을 추가하는 것이다.
8.레이아웃으로 돌아가서 최소 높이: 배너높이, 콘텐츠 양쪽 맞춤 : 정렬 위치 등을 설정한다.
9.배너 텍스트 영역을 선택해서 스타일 > 텍스트 색상 > 지구본모양은 내가 설정한 전역 색상 목록을 볼 수 있다.

## <span style="color:#ffa59c; font-weight:bold;">좌우 분리 컨테이너</span>
1.컨테이너를 좌, 우 나누어진 요소 추가
2.각 영역에 요소 추가
3.각 영역 내부에 마우스 오버하면 회색테두리 생성 => 회색 영역 레이아웃 수정, 콘텐츠에 오버하면 핑크색 테두리 생성 => 회색 영역 안 콘텐츠 내용 수정
4.콘텐츠 너비의 폭을 수정하여 왼쪽, 오른쪽의 너비를 각자 조정
5.플렉스 박스로 레이아웃 골라서 이미지 삽입
6.스타일 > 이미지 편집 > 마우스 오버 > 불투명: 1 > 필터 : 흐리기, 밝기 등 조정 > 전환기간(딜레이) > 마우스 오버 애니매이션 추가 > 그림자, 테두리 모서리 설정

## <span style="color:#ffa59c; font-weight:bold;">텍스트 여백&이미지 위에 텍스트</span>
-텍스트는 스타일 > 단락 간격 > 0으로 해야 위아래 여백이 사라진다.
-스타일 > 고정 여부 > 고정으로하면 스크롤해도 이미지는 그대로 멈춰있는 듯이 보인다.
-배경위로 텍스트를 올리는건 이미지를 배경으로 넣으면되고, 게시물처럼 썸네일 위에 텍스트를 올리는건 여백을 -로 입력한다. 모바일과 테블릿은 %로 해야 안틀어진다

## <span style="color:#ffa59c; font-weight:bold;">입력 폼</span>
-입력폼은 플러그인을 다운 받아야한다.

#### WPform
1.WPform 설치 후 활성화
2.Ultimate Kit (Style) for WPform 설치 후 활성화
3.왼쪽탭에 WPform이 생겼다. 들어가서 양식 새로추가
4.검색창에 contact 등 필요한 폼을 검색
5.간단한 문의 양식 템플릿 사용
6.수정을 원하는 곳을 클릭하여 "일반적인"에서 형식을 바꿀 수 있다.
7."고급"에서 필드 크기와 자리 표시자 텍스트에서 플레이스홀더를 설정할 수 있고 레이블 숨기기하면 라벨을 숨길 수 있다.
8.새로운 폼을 추가할 때는 "필드추가"후에 드래그하면 된다.
9.css클래스에서 레이아웃 표시를 클릭하면 입력폼의 배치를 바꿀 수 있다.
10.제출버튼을 클릭해서 버튼 커스터마이징이 가능하다.
11.미리보기 > 상단 사용자 정의 > 각 폼의 연필모양 편집 클릭하여 상세 디자인이 가능하다.
12.저장하면 엘리멘터 편집기에서 레이아웃을 추가하고 드래그해서 가져올 수 있는 항목 중에 wpform이 있다
13.수정이 다시 필요할 때는 미리보기 사용자 정의에서 찾아들어가면 된다
14.워드프레스 편집기로 나가기 > 설정 > 일반에 관리자 이메일 주소가 있는데 입력 폼에서 문의하기를 하면 여기에 설정된 이메일로 전송된다.
15.이메일을 변경하면 변경대기중 상태인데 이메일에 들어가서 확인만 눌러주면 바뀐다.

#### Fluent Forms
-Entries가 되어야 제출한 양식을 저장하고 목록을 나타낼 수 있는데 WPform은 유료고 여기는 무료이다.


## <span style="color:#ffa59c; font-weight:bold;">메인페이지 적용</span>
-모양 > 사용자 정의 > 홈페이지 설정 > 최신글에 체크되어있는것을 정적페이지로 바꾸어주면 엘리멘터에서 수정한 디자인이 적용된다.

## <span style="color:#ffa59c; font-weight:bold;">수정사항 적용 안되는 문제</span>
-파란버튼의 공개 - 발행됨으로는 적용안됨. 오른쪽 상단의 저장 버튼을 눌러야 wpform이든 추가css든 적용이 된다.

## <span style="color:#ffa59c; font-weight:bold;">페이지 템플릿화</span>
-오른쪽 상단 공개 옆 화살표메뉴 > 템플릿으로 저장 > 다른 페이지 레이아웃 추가하고 + 옆 폴더 표시를 선택해서 템플릿을 불러올 수 있다.

## <span style="color:#ffa59c; font-weight:bold;">게시판</span>
-갤러리 게시판에 첨부파일은 썸네일 용으로 상세보기에서 안보인다. 상세보기에서는 글쓰기 오른쪽 상단에 사진 버튼을 클릭해서 첨부하면된다.

#### 갤러리 게시판
1.게시판은 플러그인 망보드(mangboard) 다운로드 후 활성화
2.왼쪽 사이드메뉴에 망보드 메뉴 생성됨
3.게시판 관리 > 게시판 추가 > 게시판 이름은 영문으로 간단하게 작성(게시판 삽입할 때 이름사용)
4.목록 갯수, 페이지 블럭 갯수 등 설정하고 *게시판 권한 설정하고 확인
5.목록으로가면 코드가 쭉 있는데 갤러리 게시판을 만든다면 아래 코드만 복사
```
갤러리: [mb_board name="gallery" list_type="gallery" responsive_class="col-321" style=""]
```
5.페이지 편집창으로가서 요소 추가 쭉 내려보면 단축 코드가 있다 추가해서 단축코드 입력칸에 복사한 코드를 추가
6.코드내에서 css를 입력한다. 게시물 반응형 별 높이를 설정하려면 아래 코드처럼
```
[mb_board name="gallery" list_type="gallery" responsive_class="col-321"
height="360px" tablet_height="250px" mobile_height="200px" style=""]

!! 위코드로 적용이 안될 가능성이 높음
추가 CSS에 미디어쿼리를 추가해야 적용이 가능하다.
@media (max-width: 1024px) {
	.mb-name-gallery .img {	
		height:250px !important;
	}
}

@media (max-width: 767px) {
  .mb-name-gallery .img { height: 200px !important; }
}
```

#### 일반 게시판
1.망보드에서 board 탭메뉴 선택 > 게시판 추가 > 게시판 이름은 다르게 > 카테고리 기능도 있는데 ajax도 있고 좋아보임 나중에 살펴봄 > 일반게시판은 아래 코드만 복사
```
자료실: [mb_board name="board1" style=""]

*이 부분은 메인에 노출할때 최근 게시물만 뽑는 용도이다
최근 게시물: [mb_latest name="board1" title="board1" list_size="5" style=""]
```

#### 망보드 커스텀
-망보드 메뉴얼 > 커뮤니티에 글이 많이 올라와있다.
1. 일반 자료실 게시판에서 조회수를 안보이게 하는 숏코드
>[mb_board name="board1" hide_list="fn_hit"  title_format="name_date"]

2. 일반 자료실 게시판에서 작성자 이름을 안보이게 하는 숏코드

>[mb_board name="board1" hide_list="fn_user_name"  title_format="date_hit" hide_view="fn_user_name"]

3. 유료 자료실 게시판에서 조회수를 안보이게 하는 숏코드
>[mb_board name="board1" hide_list="fn_hit"  title_format="name_date" view_title_format="name__date"]

-게시판 항목 넓이 조정
>파일질라에 접속 후 mangboard/skins/bbs_basic/includes/skin-model.php 에서 넓이를 조정할 수 있다.



## <span style="color:#ffa59c; font-weight:bold;">파비콘 설정</span>
-모양 > 사용자 정의 > 사이트 아이덴티티 > 파비콘 업로드(최소 512x512px 이상 업로드 해야하며 자동으로 줄여준다.)

## <span style="color:#ffa59c; font-weight:bold;">운영중인 도메인에 백업, 복원 및 운영</span>
1.전체 사이트 백업 
1)UpdraftPlus 플러그인 다운로드
2)왼쪽 사이드메뉴에 추가된 플러그인으로 접속
3)지금 백업 클릭
4)데이터베이스, 플러그인, 테마, 업로드 등 각 파일 다운로드하여 저장

2.전체 사이트 복원
1)새 워드프레스 설치
2)UpdraftPlus 플러그인 다운로드
3)왼쪽 사이트메뉴에 추가된 플러그인으로 접속
4)기존 백업 > 추가작업:백업 파일 업로드 > 모든파일 올리기 > 하단에 추가되면 백업 버튼 클릭
*복원 과정에서 백업사이트 관리자 계정 정보가 들어올 수도 있음
이때 백업된 계정 그대로 유지될 수도, 새 계정으로 덮어씌워질 수도 있음
만약 로그인 안 되면 → 새 계정 또는 phpMyAdmin으로 비밀번호 초기화 가능
5)설정 > 고유주소 > 그대로 바꾸지않고 저장 (자동으로 구조를 새로 생성해줌)

3.템플릿 백업
1)전체 백업 : 도구 > 내보내기 > 나의 템플릿 (.xml확장자)
2)한 템플릿만 백업 : 템플릿 > 내보내기 템플릿 (.json확장자)

4.템플릿 복원
1)전체 복원 : 도구 > 가져오기 > WordPress 지금 설치 > 가져오기 도구 실행 > 파일선택 후 가져오기
2)한 템플릿만 복원 : 템플릿가져올 페이지 생성 > elementor 편집기 > 레이아웃에서 폴더클릭 (템플릿가져올떄처럼) > 오른쪽 상단위 업로드 아이콘 클릭 > json파일 올리기

***주의사항***
1.테마가 다르면 레이아웃이 꺠질 수 있음 (현재 아스트라면 아스트라 테마에서하는게 안전)
2.복원 과정에서 관리자 계정 정보가 덮어씌워지면 phpMyAdmin으로 비밀번호 초기화 필요
3.전체 사이트 복원후 고유주소 다시한번 저장하지않으면 깨질 수 있음
4.설치된 플러그인과 테마 메모장에 함께 저장 필수

-----Local에 사이트 저장-----
다른 사이트를 작업하다가 템플릿을 내보내기 하려면 해당 사이트가 어딘가에 복원되어있어야한다.
1개의 호스팅에는 하나밖에 운영이 안되므로 Local이라는 프로그램에서 로컬로 저장해두면 여러페이지를
사용자는 열어볼 수 없지만 로컬에서 열어볼 수 있다 여기에서 템플릿을 백업->복원 해야한다.

-----앞으로의 운영 방식-----
1.테마는 웬만하면 같은 걸로 유지
2.공유드라이버 > 웹개발팀/개발 > 워드프레스 홈페이지 백업 폴더에 사이트 백업파일 보관(전체 백업 파일과 템플릿 백업 파일)
3.자주 사용되는 템플릿은 그 페이지만(또는 영역만) 별도로 분리하여 템플릿을 만들고 .json파일로 하나씩 저장해둘것. (그룹화와 같은개념)


## <span style="color:#ffa59c; font-weight:bold;">Local 프로그램에 복원</span>
1.https://localwp.com 에서 local 설치
2.실행 후 Create a new site 
3.사이트 이름 짓기
4.나머지는 기본값, preferred로 만들기
5.php버전 7.4.x로 설정 (카페24 워드프레스가 보통 이 버전임)
6.local에 WP admin으로 새로 생성된 사이트의 관리자 페이지 접속
7.UpdraftPlus 설치
8.모든 백업 파일 업로드 후 복원
9.사이트명.local로 사이트이름 변경
10.망보드 사용이라면 게시판 추가해서 똑같은 이름으로 만들어주기(게시물이 필요하다면 호스팅센터에서 따로 DB백업해야함)

## <span style="color:#ffa59c; font-weight:bold;">SEO 설정</span>
#### 구글
1.설정 > 읽기 > "검색 엔진이 이 사이트를 검색하는 것을 차단" 체크 해제 확인 
2.워드프레스에서 Yoast SEO 플러그인 설치
3."처음 구성" 작성 
4.일반 > 사이트 표현 > 조직이름, 대체 조직 이름 작성(검색될이름)
5.Yoast SEO > 일반 > 사이트 연결 > 구글은 구글서치콘솔 > add property > URL prefix > url 입력 > html tag > 코드 복사 후 사이트 연결에 다시 붙여넣기 > verify 
6.구글 서치 콘솔 > 사이트맵 > https://kkioun.mycafe24.com/sitemap_index.xml 입력 
7.couldn't fetch 가 fetch로 바뀌면 성공

#### 네이버
1.네이버 서치어드바이저에서 웹마스터 도구로 접속
2.사이트 등록에 url넣고 HTML 태그에있는 메타 태그 복사
3.워드프레스에서 WPCode 플러그인 다운로드
4.코드 스니펫 탭 > 헤더 및 푸터 > 헤더에 복사한 것 붙여넣기
5.네이버 서치어드바이저에서 소유확인 클릭
6.등록된 사이트 목록에서 링크 클릭하여 접속 
7.요청 > 사이트맵 제출 > 사이트맵 URL 입력에 https://내도메인/sitemap.xml 입력 

#### RSS 제출
-구글은 자동으로 되므로 제출할 필요x
-네이버는 네이버 서치어드바이저 > 요청 > RSS 제출 > RSS URL 입력에 https://kkioun.mycafe24.com/feed 입력 후 제출

## <span style="color:#ffa59c; font-weight:bold;">CSS 넣기</span>
-CSS 추가는 가급적 사용하지 않는게 좋아보임 (테마 업데이트시 삭제위험, 좁은 공간 등)
-요소 + 에 html코드를 선택하여 원하는 위치에 코드박스를 넣고 css를 입력 > 적용할 대상에 클래스명 추가해주기(고급설정에서 넣어도되고 텍스트라면 직접 코드안에 텍스트 형태로 작성

## <span style="color:#ffa59c; font-weight:bold;">CSS 수정 크게보기</span>
1.Custom CSS and JS 플러그인 다운로드 후 활성화
2.왼쪽 탭에 메뉴 생성됨
3.Add Custom CSS 클릭
4.Permalink 에서 파일 이름 변경 가능
5.내용 작성 후 공개

## <span style="color:#ffa59c; font-weight:bold;">폰트 추가하기</span>
-파일을 다운로드하여 사용하는게 통상적
1.폰트 파일 다운로드 : 다운로드파일은 woff2가 용량이 더 압축되어  좋고 subset이 붙은건 한번 더 불필요한  텍스트를 걸러낸 것이므로 woff2-subset사용
2.Custom Fonts – Host Your Fonts Locally 플러그인 다운로드 > 모양에 custom fonts 메뉴 생성
3.폰트파일을 업로드해야하는데 woff타입은 업로드가 불가하므로 WP Extra File Types 플러그인 
4.설정 > Extra File Types > 맨 상단 Check only file extensions 체크 > woff, woff2 등 업로드할 확장자 체크 > 변경사항 저장 => 업로드 가능
5.모양 > Custom Fonts > Add New Font > 폰트네임 설정 > choose file > 파일업로드에 굵기별 파일 업로드 > 원하는 두께 파일 선택 > 해당하는 font-weight 선택 > add Font Variation 선택하여 모든 굵기 추가 > save font > elementor 편집기의 타이포그래피에 추가됨 
6.사용자 정의 > 기본 글꼴 설정 가능하고, 엘리멘터편집기에서 전역 글꼴 톱니버튼 클릭하여 사용자 정의 글꼴을 추가할 수 있다.

## <span style="color:#ffa59c; font-weight:bold;">영역 복사</span>
-전체 복사를 해도 되지만 이미 이미지나 텍스트 등을 넣은 상태라면 일반 복사를 한뒤에 오른쪽 클릭 > 붙여넣기 스타일 기능으로 스타일만 복사하면 된다.

## <span style="color:#ffa59c; font-weight:bold;">반응형인데 구조 다를 때</span>
-PC와 MO에서 컨테이너 배치가 다를 때 똑같은 영역을 두개 만들어서 PC는 모바일에서 안보이게, MO는 PC에서 안보이게 두 개 배치하자
-카페24의 RWB, RTMB 두 개 넣는것과 동일한 기능

## <span style="color:#ffa59c; font-weight:bold;">반응형 모바일, 테블릿 기준점 변경</span>
-왼족 상단 햄버거버튼 오른쪽 클릭 > 사이트 설정 > 레이아웃 > 중단점에서 기준점을 변경할 수 있다.
-와이드 스크린이나 테블릿 가로, 모바일 가로도 설정할 수 있다.

## <span style="color:#ffa59c; font-weight:bold;">플러그인</span>
-All-in-One WP Migration and Backup : 백업
-UpdraftPlus - 백업/복원 : 백업
-Child Theme Configurator : 차일드 테마
-Code Snippets : php등 코드 편집
-Custom Fonts : 다운로드 폰트 적용
-WP Extra File Types : 파일확장자 추가 (폰트 업로드 등)
-Elementor Website Builder : 편집기
-Fluent Forms : 입력폼 생성
-MangBoard WP : 게시판
-Simple Custom CSS and JS : css, js 큰 창 수정
Sticky Menu & Sticky Header : 헤더 고정
-Ultimate Kit ( Styler ) for WPForms : WPform 레이아웃 수정 등
-Yoast SEO :  SEO 설정
-WP Headers And Footers : head, footer, body 전역코드 삽입가능 *goat
-Smart Slider 3 : 배너 스와이퍼 등 배너마다 다른 텍스트 가능, 프로그래스바 커스텀 가능
-MarqueeX – Smooth Marquee Slider & News ticker for Gutenberg & Elementor : 흘러가는 슬라이드쇼
-Easy Updates Manager : 자동 업데이트 관리 

## <span style="color:#ffa59c; font-weight:bold;">style</span>
-style은 전역은 custom CSS and JS에, 페이지별은 엘리멘터편집창에 HTML코드에 스타일 태그 넣을 것. 그래야 백업했을때 스타일도 같이 따라온다

