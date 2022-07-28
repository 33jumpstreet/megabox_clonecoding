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


