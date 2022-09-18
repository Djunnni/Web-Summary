### CSS 선택자

CSS 선택자는 CSS 규칙을 적용할 요소를 정의합니다.

#### 기본 선택자

1. 전체 선택자

```css
* {
    // 전체 선택자
}
```

2. 유형 선택자

```css
input {
    // 유형 선택자
}
a {
}
```

3. 클래스 선택자

```css
.item {
    // 주어진 class 특성을 가진 모든 요소들을 선택합니다.
}
```

4. ID 선택자

```css
#userInfo {
    // id 특성에 따라 요소를 선택합니다. 문서내에는 주어진 ID는 하나만 있어야 한다!
}
```

5. 특성 선택자

```css
// 주어진 특성을 가진 모든 요소를 선택합니다.
img[src] {
} // src 속성을 가지고 있는 모든 요소와 일치
img[src="icon"] {
} // src에 "icon"으로 등록된 모든 요소
img[class~="icon"] {
} // icon이라는 src를 가지고 있는 요소 ex) class가 "icon profile", "profile icon" (O), "icon-profile" (X) // 여러개의 class가 함께 지정돼도 icon을 독립적으로 가지고 있다면 선택
img[class|="icon"] {
} // icon으로 시작하는 class요소만 선택하되, 하이픈으로 구분해 더 많은, 다양한 요소 선택 가능
img[src^="icon"] {
} // src 속성에서 icon으로 시작하는 모든 요소를 선택
img[src$="icon"] {
} // src 속성에서 icon으로 끝나는 모든 요소를 선택
img[src*="icon"] {
} // src에 icon을 포함하고 있으면 모든 요소 선택
```

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>Document</title>
        <style>
            .item {
                width: 100px;
                height: 100px;
                border: 1px solid gray;
            }
            div[data-src] {
                /* data-src 속성을 가지고 있으면 뒷배경: 그린 */
                background-color: green;
            }
            div[data-src|="daniel"] {
                /* 특성 선택자가 daniel로 시작하는 요소만 선택하되, 하이픈으로 다양하게 선택가능, 뒷배경: 레드 */
                background-color: red;
            }
        </style>
    </head>
    <body>
        <div class="item" data-src="daniel"></div>
        <div class="item" data-src="korea daniel"></div>
        <div class="item" data-src="daniel korea"></div>
        <div class="item" data-src="daniel-lee"></div>
        <div class="item" data-src="lee-daniel"></div>
    </body>
</html>
```

6. 그룹 선택자

선택자 목록

","는 선택자 그룹을 생성하는 방법으로 모든 일치하는 노드를 선택한다.

7. 결합자

-   자손 결합자
    "div span"div안에 위치한 모든 span 요소와 일치

-   자식 결합자
    "ul > li" ul요소 바로아래 위치하는 모든 li와 일치

-   일반 형제 결합자
    "p ~ span" p요소 뒤를 따르는 모든 span과 일치

-   인접 형제 결합자
    "h2 + p" h2 바로뒤에 p요소와 일치

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>Document</title>
        <style>
            body div {
                background: coral;
            } /* 자손 결합자 */
            body > div {
                background-color: aqua;
            } /* 자식 결합자 */
            p ~ span {
                font-style: italic;
                color: red;
            } /* 일반 형제 결합자 */
            p + span {
                color: green;
            } /* 인접 형제 결합자 */
        </style>
    </head>
    <body>
        <h2>Hello</h2>
        <p>daniel</p>
        <span>lee</span>
        <span>lee1</span>
        <span>lee2</span>
        <span>lee3</span>
        <div>
            <span>div.span</span>
            <div>
                <div>daniel</div>
            </div>
        </div>
        <span>lee4</span>
    </body>
</html>
```

8. 의사 클래스 / 요소

-   의사 클래스
    ":"로 연결되어 a:visited와 같은 클래스들
-   의사 요소
    "::first-child" 같은 클래스들
