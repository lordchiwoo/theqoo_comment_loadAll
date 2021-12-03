# theqoo_comment_loadAll


***v2.md 참조(크롬 확장프로그램)***


F12를 누르고 콘솔창에 아래 코드를 복붙한뒤 엔터.


버튼같은걸 ....음... 크롬 애드온을 만들어볼까..

``` js
let intervalID = setInterval(() => loadAllComments(), 400);

function loadAllComments() {
  if (typeof loadAllComments.counter == "undefined") {
    loadAllComments.counter = 0;
  }

  let dtp = jQuery(".show_more.comment_header").attr("data-target-page");
  if (loadAllComments.counter++ > 100 || dtp == 1) {
    clearInterval(intervalID);
    $("html, body").animate({ scrollTop: $(".comment_header_bar").eq(0).offset().top - 200 }, 2000);
  }
  
  console.log(loadAllComments.counter);

  jQuery("#cmtPosition .show_more").click();
}
```
