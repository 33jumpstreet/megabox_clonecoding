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
