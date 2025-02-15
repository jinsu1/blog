---
title: "[Javascript]Module"
date: "2024-08-29"
tags:
    - css
    - javascript
    - html
    - tab
    - menu
    - dropdown
    - accordion
thumbnail: "/assets/img/thumbnail/javascript.jpeg"
---
## <span style="color:#1E90FF; font-weight:bold;">TabMenu - CSS(노가다 버전)</span>

### HTML

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <div id="tab-container">
        <div class="tab-button-group">
            <a href="#newyork" class="tab-button active">NewYork</a>
            <a href="#london" class="tab-button">London</a>
            <a href="#paris" class="tab-button">Paris</a>
            <a href="#seoul" class="tab-button">Seoul</a>
        </div>

        <div id="newyork" class="tab-page active">
            <h3>NewYork</h3>
            <p>NewYork is the capital city of US.</p>
        </div>

        <div id="london" class="tab-page">
            <h3>London</h3>
            <p>London is the capital of England.</p>
        </div>

        <div id="paris" class="tab-page">
            <h3>Paris</h3>
            <p>Paris is the capital of France.</p>
        </div>

        <div id="seoul" class="tab-page">
            <h3>Seoul</h3>
            <p>Seoul is the capital of Korea.</p>
        </div>
    </div>
</body>
</html>
```

### CSS

```css
 body {
            font-family: Arial;
        }

        .tab-button-group{
            overflow: hidden;
            border: 1px solid #ccc;
            background-color: #f1f1f1;
            display:flex;

            .tab-button {
                display:block;
                background-color: inherit;
                min-width: 100px;
                box-sizing: border-box;
                border: none;
                outline: none;
                padding: 14px 16px;
                font-size: 17px;
                color: #222;
                text-align: center;
                text-decoration: none;
                cursor: pointer;
                transition: 0.3s;

                &:hover {
                    background-color: #ddd;
                }

                &.active {
                    background-color: #ccc;
                }
            }
        }

        .tab-page {
            display: none;
            padding: 6px 12px;
            border: 1px solid #ccc;
            border-top: none;

            &.active {
                display: block;
            }
        }
```
### javascript

```javascript
document.querySelectorAll('.tab-button').forEach((v, i) => {
            v.addEventListener('click', (e) => {
                const currentIndex = i;
                const href = e.currentTarget.getAttribute("href");

                document.querySelectorAll('.tab-button').forEach((v1, i1) => {
                    if(currentIndex == i1) {
                        v1.classList.add('active');
                    } else {
                        v1.classList.remove('active');
                    }
                });

            document.querySelectorAll('.tab-page').forEach((v2, i2) => {
                v2.classList.remove('active');
            });

            document.querySelector(href).classList.add('active');
        });
    });
```
<br>

## <span style="color:#1E90FF; font-weight:bold;">TabMenu - javascript(자동화 버전)</span>

### HTML

```html
<h1>Webtoon</h1>

<ul class="gnb">
    <li>
        <a href="07-webtoon.html?weekday=mon" data-weekday="mon">월요웹툰</a>
    </li>
    <li>
        <a href="07-webtoon.html?weekday=tue" data-weekday="tue">화요웹툰</a>
    </li>
    <li>
        <a href="07-webtoon.html?weekday=wed" data-weekday="wed">수요웹툰</a>
    </li>
    <li>
        <a href="07-webtoon.html?weekday=thu" data-weekday="thu">목요웹툰</a>
    </li>
    <li>
        <a href="07-webtoon.html?weekday=fri" data-weekday="fri">금요웹툰</a>
    </li>
    <li>
        <a href="07-webtoon.html?weekday=sat" data-weekday="sat">토요웹툰</a>
    </li>
    <li>
        <a href="07-webtoon.html?weekday=sun" data-weekday="sun">일요웹툰</a>
    </li>
</ul>

<div class="container"></div>
```

### CSS

```css
body {
        padding: 0 15px;
    }

    .gnb {
        list-style: none;
        padding: 0;
        margin: 0;
        display: flex;

        li:after {
                content: "|";
                padding: 0 7px;
                color: #ccc;
        }
        
        li:last-child:after {
            content:"";
        }

        a {
            font-size: 20px;
            text-decoration: none;
            padding-bottom: 3px;
            color: #222;

            &:hover {
                color: #22b8cf;
            }

            &.active{
                border-bottom: 3px solid #22b8cf;
                color: #22b8cf;
            }
        }        
    }

    .container {
        display:flex;

        .item {
            flex: 1;
            box-sizing: border-box;
            padding: 10px 5px;
            text-align: center;
            margin: 10px;
        }
    }
```

### Javascript

-data.js

```javascript
const webtoon = {
    mon: [
        {
            title: "참교육",
            author: "채용택/한가람",
            point: 9.86,
            thumbnail: "mon1.jpg"
        },
        {
            title: "뷰티풀 군바리",
            author: "설이/윤성원",
            point: 9.81,
            thumbnail: "mon2.jpg"
        },
        {
            title: "퀘스트지상주의",
            author: "박태준 만화회사",
            point: 9.79,
            thumbnail: "mon3.jpg"
        }
    ],

    tue: [
        {
            title: "김부장",
            author: "박태준 만화회사/정종택",
            point: 9.19,
            thumbnail: "tue1.jpg"
        },
        {
            title: "여신강림",
            author: "야옹이",
            point: 9.38,
            thumbnail: "tue2.jpg"
        },
        {
            title: "대학원 탈출일지",
            author: "요다",
            point: 9.98,
            thumbnail: "tue3.jpg"
        }
    ],

    wed: [
        {
            title: "내 남편과 결혼해줘",
            author: "LICO / 성소작",
            point: 9.95,
            thumbnail: "wed1.jpg"
        },
        {
            title: "전지적 독자 시점",
            author: "UMI / 슬리피-C",
            point: 9.95,
            thumbnail: "wed2.jpg"
        },
        {
            title: "조조코믹스",
            author: "이동건",
            point: 9.97,
            thumbnail: "wed3.jpg"
        }
    ]
};
```

```javascript
<script src="./data.js"></script>

//querystring을 객체로 변환 => querystring = "weekday=mon"
//const query = new URLSearchParams(location.search); => "weekday=mon" => const query = { weekday : "mon" }

//생성된 객체를 JSON으로 변환 => weekday=mon => const weekday = { "weekday" : "mon" }; 

const weekday  = Object.fromEntries(new URLSearchParams(location.search)).weekday;
//const { weekday } = Object.fromEntries(query);

document.querySelectorAll('.gnb a').forEach((v, i) => {
    console.log(`v.dataset.weekday: ${v.dataset.weekday}`);
    if( v.dataset.weekday == weekday ) {
        v.classList.add('active');
    } else {
        v.classList.remove('active');
    }
});

const container = document.querySelector('.container');

const currentList = webtoon[weekday];

if (currentList) {
    currentList.forEach((v, i) => {
        const item = document.createElement("div");
        item.classList.add("item");

        const img = document.createElement("img");
        img.setAttribute("src", `img/${v.thumbnail}`);
        item.appendChild(img);

        const title = document.createElement("h3");
        title.innerHTML = v.title;
        item.appendChild(title);

        const author = document.createElement("p");
        author.innerHTML = v.author;
        item.appendChild(author);

        const point = document.createElement("p");
        point.innerHTML = v.point;
        item.appendChild(point);

        console.log(item);

        container.appendChild(item);
    });
}
```


<br>


## <span style="color:#1E90FF; font-weight:bold;">Dropdown</span>

### HTML
```html
<ul class="menu-container">
    <li class="menu-item">
        <a href="#">Frontend</a>
        <ul class="sub">
            <li>
                <a href="#">HTML + CSS</a>
            </li>
            <li>
                <a href="#">Javascript</a>
            </li>
            <li>
                <a href="#">jQuery</a>
            </li>
        </ul>
    </li>
    <li class="menu-item">
        <a href="#">Backend</a>
        <ul class="sub">
            <li>
                <a href="#">PHP</a>
            </li>
            <li>
                <a href="#">JSP</a>
            </li>
            <li>
                <a href="#">Node.js</a>
            </li>
        </ul>
    </li>
    <li class="menu-item">
        <a href="#">Mobile</a>
        <ul class="sub">
            <li>
                <a href="#">iOS</a>
            </li>
            <li>
                <a href="#">Android</a>
            </li>
            <li>
                <a href="#">Hybrid</a>
            </li>
        </ul>
    </li>
</ul>

<h1>Hello World</h1>

```
### CSS

```css
 body {
    background-color:#dad9d9;
}
.menu-container{
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;

    a {
        display: block;
        width: 179px;
        height: 48px;
        background-color: white;
        line-height: 48px;
        text-align: center;
        font-weight: bold;
        color: black;
        text-decoration: none;

        &:hover {
            background-color: #aaaaaa;
        }
    }

    .menu-item {
        flex: 0 0;
        position: relative;

        .sub {
            list-style: none;
            margin: 0;
            padding: 0;
            position: absolute;
            border-radius: 5px;
            z-index: 1000;
            max-height: 0;
            overflow: hidden;
            transition: max-height 180ms ease-out;
        }
    }
}
```
### Javascript

```javascript
document.querySelectorAll('.menu-item').forEach((v, i) => {
    v.addEventListener('mouseover', (e) => {
        const current = e.currentTarget;
        const sub = current.querySelector('.sub');
        sub.style.maxHeight = sub.scrollHeight + 'px';
    });

    v.addEventListener('mouseout', (e) => {
        const current = e.currentTarget;
        const sub = current.querySelector('.sub');
        sub.style.maxHeight = '0px';
    });
});
```
<br>

## <span style="color:#1E90FF; font-weight:bold;">Accordion</span>

### HTML

```html
<h2>Animated Collapsibles</h2>
    <p>A Collpasible:</p>
    <div class="collapse">
        <h1 class="collapsible-title">Open Collapsible</h1>
        <div class="content">
            <p>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Doloribus officia voluptatum magni dolore optio vitae corporis, voluptate repellat suscipit quod incidunt illum eum dolor eveniet ab nostrum voluptates laboriosam vero?
            </p>
        </div>
    </div>
    <div class="collapse">
        <h1 class="collapsible-title">Open Collapsible</h1>
        <div class="content">
            <p>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Doloribus officia voluptatum magni dolore optio vitae corporis, voluptate repellat suscipit quod incidunt illum eum dolor eveniet ab nostrum voluptates laboriosam vero?
            </p>
        </div>
    </div>
```
### CSS

```css
 .collapsible-title {
    background-color: #777;
    color: white;
    cursor: pointer;
    padding: 18px;
    width: 100%;
    border: none;
    font-weight: normal;
    margin: 0;
    text-align: left;
    outline: none;
    font-size: 15px;

    &.active, &:hover {
        background-color: #555;
    }
}

.content {
    padding: 0 18px;
    max-height:0;
    overflow: hidden;
    transition: max-height 0.2s ease-out;
    background-color: #f1f1f1;
}
```
### Javacript

```javascript
 document.querySelectorAll(".collapsible-title").forEach((v, i) => {
    v.addEventListener('click', (e) => {
        document.querySelectorAll('.content').forEach((w, j) => {
            w.style.maxHeight = null;
        });
        const current = e.currentTarget;
        
        current.classList.toggle("active");


        document.querySelectorAll('.collapsible-title').forEach((w,j) => {
            if( w !== current) {
                w.classList.remove('active');
            }
        });

        const parent = current.closest(".collapse");
        const content = parent.querySelector(".content");
        
        if( !current.classList.contains('active')) {
            content.style.maxHeight = null;
        } else {
            content.style.maxHeight = content.scrollHeight + 'px';
        }
    });
});
```
<br>

## <span style="color:#1E90FF; font-weight:bold;">주민번호</span>

### HTML

-앞자리는 6자까지만 입력가능, 앞자리 모두 입력 후 뒷자리 입력 칸으로 focus

```html
<form id="myform">
    <h3>주민번호를 입력하세요.</h3>
    <input type="text"  name="jumin1" id="jumin1" class="jumin" />
    ---
    <input type="password"  name="jumin2" id="jumin2" class="jumin" />
</form>
```

```javascript
document.querySelectorAll(".jumin").forEach((v, i) => {
    v.addEventListener("focus", e => {
        e.currentTarget.style.backgroundColor = '#006';
        e.currentTarget.style.color = '#fff';
    });

    v.addEventListener("blur", e => {
        e.currentTarget.style.backgroundColor = '#fff';
        e.currentTarget.style.color = "#000";
    });
});

document.querySelector("#jumin1").addEventListener('keyup', e => {
    const value = e.currentTarget.value;

    if(value.length >= 6) {
        e.currentTarget.value = value.substring(0, 6);
        document.querySelector("#jumin2").focus();
    }
});
```
<br>

## <span style="color:#1E90FF; font-weight:bold;">팝업창 띄우기</span>

-window.open('주소', '창이름', '속성'); 으로 구성 속성은 대부분 공통으로 들어간다.
-팝업창이름을 같게하면 같은 창을 재활용한다.
-interval에 창 띄우기를 적용하면 설정한 시간마다 창을 띄울 수 있다.

```javascript
document.querySelector('#link3').addEventListener('click', e =>  {
    e.preventDefault();

    window.open('https://www.naver.com', 'mypop', 'width=500, height=500, scrollbars=no, toolbar=no, menubar=no, status=no');
});
```
<br>

## <span style="color:#1E90FF; font-weight:bold;">웹 브라우저, 모바일 식별</span>

```html

<h1 id="browser"></h1>
<h1 id="mobile"></h1>

<script>
    function getWebBrowserName() {
        //전부 소문자로 변경해야 용이함
        //uset Agent == HTTP 요청을 보내는 디바이스와 브라우저 등 사용자 소프트웨어의 식별 정보
        let agt = navigator.userAgent.toLowerCase();

        //indexOf는 해당 문자열이 있는 위치의 시작점을 반환하며 없으면 -1을 반환
        if(agt.indexOf('edge') != -1) {
            return 'Edge';
        } else if (agt.indexOf('chrome') != -1) {
            return 'Chrome';
        } else if (agt.indexOf('netscape') != -1 ) {
            return 'Netscape';
        } else {
            return 'Unknown';
        }
    }

    function isMobile() {
        let tmpUser = navigator.userAgent.toLowerCase();
        let isMobile = false;

        if(tmpUser.indexOf("iphone") > -1 || tmpUser.indexOf("ipad") > -1 || tmpUser.indexOf("ipod") >  -1 || tmpUser.indexOf("android") > -1) {
            isMobile = true;
        }

        return isMobile;
    }

    document.getElementById("browser").innerHTML = getWebBrowserName();
    document.getElementById("mobile").innerHTML = isMobile();
</script>
```
<br>

## <span style="color:#1E90FF; font-weight:bold;">이전 페이지 이동</span>

```javascript
document.querySelector("#link1").addEventListner('click', e => {
    e.preventDefault();
    history.back(); // history.forward();
});
```
<br>

## <span style="color:#1E90FF; font-weight:bold;">페이지 이동</span>

```javascript
location.href = 'https://www.naver.com'; // 페이지 및 파일 이동
location.reload(); // 페이지 새로고침
```

<br>

## <span style="color:#1E90FF; font-weight:bold;">팝업창 - javascript</span>


### HTML
```html
<h1>팝업창 열기</h1>

<div class="popup">
    <h2>팝업 입니다.</h2>
    <hr />
    <label>
        <input type="checkbox" id="no-open" value="Y" />
        15초간 이 창을 열지 않음
    </label>
    <button type="button" id="close-popup">닫기</button>
</div>
```
### CSS

```css
.popup {
    border: 1px solid black;
    background-color: #eee;
    box-shadow: 0 0 10px #000;
    padding: 15px;
    position: absolute;
    width: 280px;
    height: 300px;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    z-index: 9999999;

    display: none;
}
```

### Javascript

```javascript
const getCookie = (name) => {
    const regex = new RegExp("(?:^|; )" + name.replace(/([\.$?*|{}\(\)|[|]\\\/\+^])/g, "\\$1") + "=([^;]*)");

    let matches = document.cookie.match(regex);

    return matches ? decodeURIComponent(matches[1]) : undefined;
};

const setCookie = (name, value, maxAge) => {
    const encName = encodeURIComponent(name);
    const encValue = encodeURIComponent(value);
    let updatedCookie = `${encName}=${encValue};`;

    //유효경로 설정
    updatedCookie += "path=/;";
    //updatedCookie = "domain=.naver.com" 쿠키 전역 설정

    //유효시간은 파라미터가 전달된 경우만 설정
    //파라미터가 전달 안된 경우 설정되지 않기 때문에 브라우저를 닫기 전까지 유지
    if(maxAge !== undefined) {
        updatedCookie += `max-age=${maxAge}`;
    }

    //저장
    document.cookie = updatedCookie;
    
};

//쿠키가 저장되어 있지 않다면 레이어 팝업을 화면에 표시함
// --> 쿠키가 저장되어 있다면 if문을 건너뛰므로 팝업을 표시하지 않음
if (!getCookie("no-popup")) {
    document.querySelector(".popup").style.display = "block";
}

//닫기 버튼 이벤트
document.querySelector("#close-popup").addEventListener('click', e => {
    document.querySelector(".popup").style.display = "none";

    //체크가 되었다면 쿠키를 생성 -> 새로고침되었을 때 47라인의 코드가 실행되지 않음
    if(document.querySelector("#no-open").checked) {
        setCookie("no-popup", "Y", 15);
        //오늘 하루 이 창 열지 않음인 경우 24시간으로 설정
        //setCookie("nopopup", "Y", 60*60*24);
    }
});
```

## <span style="color:#1E90FF; font-weight:bold;">input 박스 focus 이벤트</span>

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>입력창</title>
    <style>

    .container_w1200 {
        margin-top: 80px;
        width: 1200px;
        margin: 80px auto 0;
    }

    .input_box{
        appearance: none;
        width: 100%;
        border: 0;
        padding: 28px 0 20px;
        font-size: 18px;
        color: var(--color-black-3);
        font-weight: 700;
        transition: all .15s ease;
        border-bottom: 1px solid #e1e1e1;
        outline: none;
    }
        
    .placeholder {
        font-size: 18px;
    }

    .placeholder_hide {
        font-size: 14px;;
    }

    .input_label {
        position: relative;
        font-size: 14px;
        color: var(--color-silver);
        display:flex;
    }

    .input_label:focus-within {

        .input_focus_line::before{
            width: 50%;
        }

        .input_focus_line::after {
            width: 50%;
        }

        .placeholder {
            top:0px;
            font-size:14px;
            color: rgb(181, 181, 181);

            .placeholder_hide {
                display: none;
            }
        }
    }

    .input_focus_line::before {
        position: absolute;
        bottom: 0;
        left: 50%;
        width: 0;
        height: 2px;
        background-color: blue;
        content: "";
        transition: .4s;
        -webkit-transition: all .4s ease;
    }

    .input_focus_line::after {
        position: absolute;
        bottom: 0;
        right: 50%;
        width: 0;
        height: 2px;
        background-color: blue;
        content: "";
        transition: .4s;
        -webkit-transition: all .4s ease;
    }

    .placeholder {
        position: absolute;
        top: 30px;
        left: 0;
        font-size: 18px;
        transform-origin: 0 0;
        transform: translateZ(0);
        transition: all .2s ease;
        pointer-events: none;
        color: #888;
        z-index: 1;
    }


    .find {
        padding: 72px 0;
        margin: 0 306px;
    }

    </style>
</head>    
<body>
    <div class="container_w1200">
        <div class="find">
            <div id="find_id" class="tab_page tab_page_active">
                <form action="#">
                    <label for="userName" class="input_label">
                        <input type="text" class="login_box" placeholder="" />
                        <div class="input_focus_line">
                            <span class="placeholder">이름<span class="placeholder_hide">( 띄어쓰기 없이 입력하세요. )</span>
                        </div>
                    </label>
                </form>
            </div>
        </div>
    </div>   
</body>
</html>
```