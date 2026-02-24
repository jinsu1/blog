---
title: "[jQuery4]"
date: "2025-01-16"
thumbnail: "/assets/img/thumbnail/jquery4.webp"
---

# <span style="color:#eee; font-weight:bold;">jQuery4</span>

## <span style="color:#ffa59c; font-weight:bold;">자주 사용하는 함수</span>

-$("선택자").on(click, 콜백함수)
(mouseover -> mouseenter, mouseeout -> mouseleave)   
-$("선택자").attr("속성") => getter
-$("선택자").attr("속성", "값") => setter
-$("선택자").addClass(클래스명)    
-$("선택자").removeClass(클래스명)   
-$("선택자").hasClass(클래스명)   
-$("선택자").toggleClass(클래스명)   

## <span style="color:#ffa59c; font-weight:bold;">요소 찾기</span>
#### 부모 요소 찾기
```js
$(".find-parent").on("click", (e) => {
    e.preventDefault();
    
    const current = $(e.currentTarget);
    const color = current.data("color");
    const parent = current.parent();
    parent.css("background-color", color);
});
```
> js의 addEventListener 는 on 과 같다.
> data-color="#fff"과 같은 dataset의 탐색은 data("color")를 사용한다.
> .parent()로 쉽게 부모를 찾을 수 있다.
> .style 은 .css("속성", "값"); 으로 수정할 수 있다.
> .parents()는 조상을 찾는다.

<br />

#### 자식 요소 찾기
```js
$("#btn1").on("click", () => {
    const children = $("#list").children();
    children.each((i, v) => $(v).css("background-color", "#0066ff"));
    children.eq(2).css("background-color", "#ff6600");
});

$("#btn2").on("click", (e) => {
    $("#two > ul").children().each((i, v) => $(v).css("font-weight", 900));
})
```
>querySelectAll처럼 전체탐색을 따로 명령하지 않아도 자동으로 반복을 돌며 전체를 탐색한다.
>.childen() 으로 자식을 찾을 수 있다.
>forEach 대신 each를 사용한다.
>v, i -> i, v 로 위치가 바뀌니 주위
>eq(인덱스번호)를 사용해 하나만 선택할 수 있다.

<br />

#### 자손 요소 찾기
```js
 $("#btn1").on("click", (e) => {
    $("#post1").find(".thumb").each((i, v) => {
        $(v).css({
            color: "#06f",
            fontWeight: "bold"
        });
    });

    $("#post2").find(".thumb").eq(2).css({
        color: "#f60",
        fontWeight: "bold"
    });
});
```

> post1 아래 li안의 span이 thumb일 때 find를 사용하여 탐색하면 자손까지도 찾아간다.
> css를 여러줄 입력할 때는 json형태로 한다.

