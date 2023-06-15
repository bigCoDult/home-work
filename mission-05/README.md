sprite 실습 과제입니다.

본 레포지토리는 아래의 파일을 포함합니다
{rank.png,  README.md,  sprite.css,  sprite.html}



[html]

h3과 ol, 더보기를 div.ranking_box를 이용하여 블록으로 묶었습니다.

ol의 하위요소를 클릭했을때 링크로 이어지게 하기 위해,
li, 등락_아이콘을 a태그로 묶었습니다. 

논리적인 구성상 
상위로 랭크된 인기사이트를 확인하고 나서,
더보기를 이용하게 될 것이기 때문에,
ol 아래에 span으로 묶은 더보기를 배치하였습니다.



[css]

ol의 오더 넘버는 
list-style-type: none;
을 이용해 비활성화 하였고,

counter-reset: index;
를 이용해 index라는 카운터를 초기화 했습니다.

li::before 가상선택자에서
counter-increment: index;
를 이용해 index는 적용될때마다 값이 증가하게 하였고

li::before는 각각의 li요소 직전에 동작하여
content: counter(index);
가 오더 넘버를 대체하게 됩니다.



li와 등락 아이콘을 하위로 가지는 a태그를 div로 묶고

li를 좌측정렬 하기위해
position: absolute;
left: 0;
를 이용했고,

등락 아이콘을 우측정렬 하기위해
position: relative;
right: 0;
를 이용하였습니다.



icon__all 클래스를 등락아이콘에 공통적으로 부여하여
등락 상황별 기호에 공통으로 적용되는 양식을 적용하였습니다

sprite 이미지에서 필요한 부분만 가져오기 위해
.icon__up
background-position: 0 0;

.icon__stay
background-position: 0 -22px;

.icon__down
background-position: 0 -44px;
를 적용하였습니다.
