### [HTML] Node, Element 차이

#### Node란?

-   HTML DOM은 노드(Node)라고 불리는 계층적 단위에 정보를 저장하고 있다.
-   DOM은 이런 노드들을 정의하고 관계를 설명하는 역할을 한다.

HTML 문서의 정보는 노드 트리(Node Tree)라고 불리는 계층적 구조에 저장됩니다.

노드 트리는 최상위 레벨인 루트 노드(Root Node)로 부터 시작되며 낮은 레벨인 TextNode까지 뻗어간다.

| 자바스크립트에서는 DOM을 활용해 노드 트리에 포함된 모든 노드에 접근할 수 있다.

##### 노드의 종류

1. 문서 노드(Document Node)
    - HTML 문서 전체를 나타내는 노드
2. 요소 노드(Element Node)
    - 모든 HTML요소는 요소 노드이며, 속성을 가질 수 있는 유일한 노드다.
3. 속성 노드(Attribute Node)
    - 모든 HTML요소의 속성은 속성노드이며, 요소 노드에 관한 정보를 가지고 있다. 단, 해당 요소의 자식 노드에는 포함되지 않는다.
4. 텍스트 노드(Text Node)
    - HTML 문서의 모든 텍스트는 Text 노드다.
5. 주석 노드(Comment Node)
    - HTML문서의 모든 주석은 주석 노드다.

##### 노드 간 관계

1. 형제 노드(Sibling Node)
    - 같은 부모 노드를 가지는 모든 노드들
2. 조상 노드(Ancestor Node)
    - 부모노드를 포함해 계층적으로 현재 노드보다 상위에 존재하는 모든 노드
3. 자손 노드(Descendant Node)
    - 자식 노드를 포함해 계층적으로 현재보다 낮은 하위 노드들

##### 노드의 대표적인 프로퍼티

대부분이 readOnly이나 textContent는 아님.

1. childNodes
2. firstChild
3. lastChild
4. nextSibling
5. nodeType
6. parentNode
7. textContent(\*)

> 간단하게 정리해보면,
> HTML의 요소들은 노드로 구성되어있어 트리구조(DOM)로 이루어져 있다. Node는 어떻게 보면 인터페이스로 Element는 구현체이다. 그 이유는 속성, 요소, 텍스트를 가지고 있기 때문이다.

#### Element란?

-   Element는 Document안에 모든 객체가 상속하는 범용적인 클래스로 HTMLElement, SVGElement 인터페이스가 있다.

![node-element-구조](../img/element-node%EA%B5%AC%EC%A1%B0.png)

#### Element의 속성

1. classList
2. className
3. id
4. innerHTML
5. innerText
6. scrollTop, scrollLeft 등
7. tagName

#### Element 메서드

1. addEventListener
2. removeEventListener
3. getAttribute
4. hasAttribute
5. insertAdjacentHTML
6. querySelectorAll
7. getElementById
8. requestFullScreen

### 정리

정리해보면 HTML은 Node들로 이루어져 있으며 Node중 요소노드를 Element라고 한다. 그리고 Element내에서 HTMLElement, SVGElement등 다양한 요소노드들을 통해서 페이지를 개발한다.

요소노드는 Attribute를 가질 수 있는 속성 노드이기도 하기 때문에 Style등의 속성을 가질 수 있으며 이는 자식에게 영향을 미치지 않는다.
