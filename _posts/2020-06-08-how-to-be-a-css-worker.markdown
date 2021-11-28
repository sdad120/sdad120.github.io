---
layout: post
title:  "怎么成为一个CSS熟练工"
date:   2020-06-08 13:09:42 +0800
---
- 统计大站用到的属性？
- 常见的UI库到底实现了些什么？
- 排版方面到底要学一些什么？

```js
const countMap = new Map();
for (let i = 0; i < document.styleSheets.length; ++i ) {
  for (let j = 0; j < document.styleSheets[i].cssRules.length; ++ j) {
    let cssRule = document.styleSheets[i].cssRules[j];
    if (!cssRule.style) continue;
    for (let k = 0; cssRule.style[k]; ++ k) {
      if (countMap.has(cssRule.style[k])) {
        countMap.set(cssRule.style[k], countMap.get(cssRule.style[k]) + 1);
      } else { 
        countMap.set(cssRule.style[k], 1); 
      }
    }
  }
}
const sortedArray = Array.from(countMap).sort((fi, se) => se[1] - fi[1]);
```
一直被称作感性语言的CSS，最重要的便是千变万化的属性。我尝试用类似统计英语语言词频的方式，在各大产商的页面中统计常用的属性的“词频”。

怎么下载旧版Chromuium [Version List][chromuium-version-list], [Instruction][chromuium-inst]
但是不怎么work，[浏览器会block跨域的访问][can-not-css-rule]，找了老版本虽然不会报错还是会显示null。

只好使用[本地parser][css-parser#]去parse css文件。

```
[ 'display', 194 ],
[ 'color', 180 ],
[ 'height', 170 ],
[ 'position', 130 ],
[ 'font-size', 126 ],
[ 'width', 122 ],
[ 'line-height', 105 ],
[ 'background', 90 ],
[ 'padding', 82 ],
[ 'top', 71 ],
[ 'overflow', 63 ],
[ 'background-color', 51 ]
```

Display
```
[ 'display: block', 70 ],
[ 'display: -webkit-box', 30 ],
[ 'display: flex', 23 ],
[ 'display: inline-block', 22 ],
[ 'display: none', 18 ],
[ 'display: -ms-flexbox', 13 ],
[ 'display: -webkit-flex', 6 ],
[ 'display: -moz-box', 4 ],
[ 'display: none!important', 2 ],
[ 'display: flex!important', 1 ],
[ 'display: -webkit-box!important', 1 ],
[ 'display: box', 1 ],
[ 'display: inline', 1 ],
[ 'display: -ms-flexbox!important', 1 ],
[ 'display: -webkit-flex!important', 1 ]
```

知道了这些信息后要怎么去学习CSS呢？

MDN

- 几个主题
- 什么东西是需要理解的？什么东西是只要`搜索`就好

模型，display里的两种模型，block，flex
具体的值代表什么效果

- 研究什么还有价值？为什么？

很小的一块，目的是
- 让人人都能快速写UI，不花费大量时间。

More about CSS
- 用CSS动画取代JS动画，提升性能

[chromuium-version-list]: https://sourceforge.net/projects/osxportableapps/files/Chromium/
[chromuium-inst]: https://www.chromium.org/getting-involved/download-chromium
[css-parser]: https://www.npmjs.com/package/css
[can-not-css-rule]: https://stackoverflow.com/questions/48753691/cannot-access-cssrules-from-local-css-file-in-chrome-64/49160760#49160760