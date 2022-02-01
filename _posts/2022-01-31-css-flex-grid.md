---
layout: post
title: "CSS Flex"
date: 2022-01-31 22:02 +0900
categories: [TIL, CSS]
tags: [css, flex]
---

## Flexbox

1차원 레이아웃으로 주로 종, 횡으로 연속된 공간을 만든다.  
상위 컨테이너 안의 항목이 수평 및 수직으로 자동 정렬 할 수 있다.  
수직 중앙 정렬 및 등축 column생성하기 등의 문제를 쉽게 해결해준다.  
float를 대체하기에 완벽하며 코드를 더 적고 깔끔하게 쓸 수 있다.

`display: Flex`

```css
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

## Flex container의 속성

`gap`  
컨테이너 아래 항목간에 공간을 만든다

`justify-content: flex-start`  
주축을 기준으로 항목을 정렬한다(horizontally)

`align-items: stretch`  
교차축을 기준으로 항목을 정렬한다(vertically)

`flex-direction: row`  
주축을 변경한다

```css
.footer-nav {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 2.4rem;
}
```

## Flex items의 속성

`align-self: auto`  
항목이 독립적으로 align-items속성을 덮어쓴다

`flex: 0 1 auto`  
순서대로 flex-grow, flex-shrink, flex-basis의 축약으로 사용
