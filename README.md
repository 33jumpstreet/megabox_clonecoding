# megabox_clonecoding
웹 스토리보이님의 강의 보면서 실습하였습니다.

### 1. float
- 영역을 잡을 때 사용한다. 문제는 float을 사용시, height가 0이 되면서 영역이 깨진다. 이를 해결하기 위하 height가 인식할 수 있도록 해야 한다. 
- 해결방법 4가지
1) 깨지는 영역에 똑같이 float: left를 사용한다. -> 비추 
2) clear: both를 사용한다. -> 비추
3) 상위 박스에 overflow: hidden을 사용한다. -> 가끔 사용하는데, 이유는 overflow:hidden을 사용한 영역에 메뉴를 사용하면 안 보일 수 있기 때문이다. 
4) float을 사용한 상위 박스에 clearfix를 설정
'''
/* clearfix */
.clearfix{*zoom:1;} //ie7 
.clearfix:before, .clearfix:after {display: block; content: '';line-height: 0;}
.clearfix:after {clear: both;}
'''

### 2. ir효과
- 이미지를 표현하는 방법에는 img와 baclground 속성으로 표현이 가능
- img는 이미지가 의미가 있는 경우, background는 이미지가 의미 없는 경우 주로 사용된다. 
- background를 사용해서 이미지를 표현하는 경우 대체문자를 표현할 수 없기 때문에, 이때 IR효과를 사용한다. 
```
/* IR 효과 */
.ir_pm {display:block; overflow:hidden; font-size:0; line-height:0; text-indent:-9999px;} /* 의미있는 이미지의 대체 텍스트를 제공하는 경우(Phark Method) */
.ir_wa {display:block; overflow:hidden; position:relative; z-index:-1; width:100%; height: 100%;} /* 의미있는 이미지의 대체 텍스트로 이미지가 없어도 대체 텍스트를 보여주고자 할 때(WA IR) */
.ir_su {overflow: hidden; position:absolute; width:0; height:0; line-height:0; text-indent:-9999px;} /* 대체 텍스트가 아닌 접근성을 위한 숨김 텍스트를 제공할 때 */
```

### 3. 미디어쿼리 
- 반응형 웹 페이지를 제작하려면 뷰포트와 미디어 쿼리를 사용해야 합니다. 
- 뷰포트는 피시 화면 비율을 모바일 비율로 바꾸어 주고 미디어 쿼리는 화면 크기에 따라 CSS를 제작합니다. 
```
@media 미디어 쿼리의 시작을 의미
only/not only는 미디어쿼리를 지원하는 브라우저에서만 해석하고 not은 반대를 의미
media type 미디어 유형을 설정
and/, and는 둘다 조건에 맞아야 하고 ,는 하나만 맞아도 실행합니다. (and/or 개념)
조건문/실행문 화면 크기의 조건을 설정하고 그에 따른 실행문을 작성합니다.
```
- 미디어 쿼리 적용방법
1. 외부 링크에서 사용하는 방법 ( 제일 많이 사용)
```
<link rel="stylesheet" href="style/css">
```
2. 화면 크기별로 CSS 작성
```
<link rel="stylesheet" media="all and(min-width:380px)" href="style.css" />
```
3. 임포트 시키는 방법
```
@import url(style.css)all and (min-width:380px);
```
