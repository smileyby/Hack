<!-- Editor:YBY -->
<!-- 自动生成目录 -->
[TOC]

## 什么是Hack技术？
> 由于不同的浏览器，比如Internet Explorer 6,Internet Explorer 7,Mozilla Firefox等，对CSS的解析认识不一样，因此会导致生成页面的效果不一样，得不到我们所需要的页面效果。
>  这个时候我们就需要针对不同的浏览器去写不同的CSS,让他们能同事兼容不同的浏览器，能在不同的浏览器中也能得到我们想要的效果 
>  这个针对不同的浏览器写不同的CSS code的过程，就叫CSS Hack，也叫写CSS Hack。
>  注：一般是将识别能力强的浏览器的CSS写在后面
##   主流浏览器Hack写法
#### 一、Chrome浏览器
> 选择器Hack
> 
>   /\* Chrome 24- and Safari 5- \*/
>   ::made-up-pseudo-element, .selector {
>     代码放在这里
>   }
>   
>   媒体查询Hacks
>   
>   /\* Chrome, Safari 3+ \*/
>   @media screen and (-webkit-min-device-pixel-ratio:0) {
>     代码放在这里
>   }
>   
>   JavaScript Hack
>   
>   /\* Chrome \*/
>   var isChrome = Boolean(window.chrome);
#### 二、FireFox浏览器
>  属性选择器Hack
>  
>  /\* Firefox 1.5 \*/
>  bode:empty .selector {
>    样式代码放在这里
>  }
>  
>  /\* Firefox 2+ \*/
>  .selector, x:-moz-any-link {
>    样式代码放在这里
>  }
>  
>  /\* Firefox 3+\*/
>  .selector, x:-moz-any-link; x:default {
>    样式代码放在这里
>  }
>  
>  /\* Firefox 3.5+ \*/
>  body:not(:-moz-handler-blocked) .selector {
>    样式代码放在这里
>  }
>  
>  媒体查询Hack
>  
>  /\* Firefox 3.5+, IE9/10 Opera \*/
>  @media screen and (min-resolution: +72dpi) {
>    样式代码放这里
>  }
>  
>  /\* Firefox 3.6+ \*/
>  @media screen and (-moz-image-in-menus:0) {
>    样式代码放这里
>  }
>  
>  /\* Firefox 4+ \*/
>  @media screen and (min--moz-device-pixel-ratio:0) {
>    样式代码放这里
>  }
>  
>  JavaScript Hack
>  
>  /\* Firefox \*/
>  var isFF = !!navigator.userAgent.match(/firefox/i);
>  
>  /\* Firefox 2 - 13 \*/
>  var isFF = Boolean(window.globalStorage);
>  
>  /\* Firefox 2/3 \*/
>  var isFF = /a/[-1] == 'a';
>  
>  /\* Firefox 3 \*/
>  var isFF = (function x() {} ) [-5] == 'x';
>  
>  混合型Hack
>  /\* Firefox 3+ \*/
>  @-moz-document url-prefix() {
>    样式代码放这里
>  }

#### 三、Opera浏览器

>  属性选择器Hack
>  
>  /\* Opera 9.25, Safari 2/3.1 \*/
>  *|html[xmlns*=''] .selector {
>    样式代码放这里
>  }
>  
>  /\* Opera 9.27 and below, Safari 2 \*/
>  html:first-child .selector {
>    样式代码放这里
>  }
>  
>  /\* Opera 9.5+ \*/
>  noindex:-o-prefocus, .selector {
>    样式代码放这里
>  }
>  
>  媒体查询Hack
>  
>  /\* Opera 7 \*/
>  @media all and (mid-width: 0px) {
>    样式代码放这里
>  }
>  
>  /\* Opera 12- \*/
>  @media all and (-webkit-min-device-pixel-ratio:10000), not all and (-webkit-min-device-pixel-ratio:0) {
>    样式代码放这里
>  }
>  
>  /\* Opera, Firefox 3.5+, IE 9/10 \*/
>  @media screen and (mid-resolution: +72dpi) {
>    样式代码放这里
>  }
>  
>  /\* Oprea, IE 8/9/10 \*/
>  @media screen {
>    样式代码放这里
>  }
>  
>  JavaScript Hack
>  
>  /\* Opera 9.64- \*/
>  var isOpera = /^function \(/.test([].sort);
>  
>  /\* Opera 12- \*/
>  var isOpera = Boolean(window.opera);

#### 四、Safari浏览器

>  属性选择器Hack
>  
>  /\* Safari 2/3 \*/
>  html[xmlns*=''] body:last-child .selector {
>    样式代码放这里
>  }
>  html[xmlns*='']:root .selector {
>    样式代码放这里
>  }
>  
>  /\* Safari 2/3.1, Opera 9.25 \*/
>  *|html[xmlns*=''] .selector {
>    样式代码放这里
>  }
>  
>  /\* Safari 5- and Chrome 24- \*/
>  ::made-up-pseudo-element, .selector {
>    样式代码放这里
>  }
>  
>  媒体查询Hack
>  /\* Safari \*/
>  var isSafari = /a/._proto_==' //';

#### 五、IE浏览器
>  选择器Hack
>  
>  /\* IE6 and below \*/
>  *html .selector {
>    样式代码放这里
>  }
>  
>  // .suckyie6 can be any unused class
>  .suckyie6.selector {
>    样式代码放这里
>  } 
>  
>  /\* IE7 and below \*/
>  .selector, {
>    样式代码放这里
>  }
>  
>  /\* IE 7 \*/
>  *:first-child+html .selector {
>    样式代码放这里
>  }
>  .selector, x:-IE7 {
>    样式代码放这里
>  }
>  *+html .selector {
>    样式代码放这里
>  }
>  
>  /\* Everything but IE 6 \*/
>  html > body .selector {
>    样式代码放这里
>  }
>  
>  /\* Everything but IE 6/7 \*/
>  html > /**/body .selector {
>    样式代码放这里
>  }
>  
>  /\* Everything but IE 6/7/8 \*/
>  :root *> .selector {
>    样式代码放这里
>  }
>  body:last-child .selector {
>    样式代码放这里
>  }
>  body:bth-of-type(1) .selector {
>    样式代码放这里
>  }
>  body:first-of-type .selector {
>    样式代码放这里
>  }
>  
>  属性/属性值  Hack
>  
>  /\* IE  6 \*/
>  .selector {_color: blue;}
>  .selector {-color: blue;}
>  
>  /\* IE6/7 - any combination of these characters: ! $ & * ( ) = % + @ , . / ` [ ] # ~ ? : < > |  \*/
>  .selector { !color: blue; }
>  .selector { $color: blue; }
>  .selector { &color: blue; }
>  .selector { *color: blue; }
>  /\* ... \*/
>  
>  /\* IE6/7 acts as an !important \*/
>  .selector { color: blue !ie;}
>  /\*  string after ! can be anything \*/
>  
>  /\* IE8/9 \*/
>  .selector { color: blue\0/;}
>  /\* must go at the END of all rules \*/
>  
>  /\* IE 9/10 \*/
>  .selector:nth-of-type(1n) { color: blue\9; }
>  
>  /\* IE 6/7/8/9/10 \*/
>  .selector { color: blue\9; }
>  .selector { color/*\**/: blue\9; }
>  
>  /\* Everything but IE 6 \*/
>  .selector { color/**/: blue; }
>  
>  媒体查询Hack
>  
>  /\* IE 6/7 \*/
>  @media screen\9 {
>    样式代码放这里
>  }
>  
>  /\* IE 6/7/8 \*/
>  @media \0screen\, screen\9 {
>    样式代码放这里
>  }
>  
>  /\* IE 8 \*/
>  @media \0screen {
>    样式代码放这里
>  }
>  
>  /\* IE 8/9/10 & Oprea \*/
>  @media screen\0 {
>    样式代码放这里
>  }
>  
>  /\* IE 9/10, Firefox 3.5+, Opera \*/
>  @media screen and (min-resolution: +72dpi) {
>    样式代码放这里
>  }
>  
>  /\* IE 9/10 \*/
>  @media screen and (mid-width0\0) {
>    样式代码放这里
>  }
>  
>  /\* IE 10+ \*/
>  @media screen and (-ms-high-contrast: active), (-ms-high-contrast: none) {
>    样式代码放这里
>  }
>  
>  /\* Everything but IE 6/7/8 \*/
>  @media screen and (min-width: 400px) {
>    样式代码放这里
>  }
>  
>  JavaScript Hack
>  
>  /\* IE <= 8 \*/
>  var isIE = '\v'=='v';
>  
>  /\* IE 6 \*/
>  (checkIE = document,createElement('b')).innerHTML = '<!-- [if IE 7] ><i></i><![endif]-->';
>  var isIE = checkIE.getElementsByTagName('i').length == 1;
>  navigator.appVersion.indexOf('MSIE 7.') != -1;
>  
>  /\* IE 8 \*/
>  (checkIE = document.createElement('b')).innerHTML = '<!-- [if IE 8] ><i></i><![endif]-->'
>  var isIE = checkIE.getElementsByTagName("i").length == 1;
>  
>  /\* IE 9 \*/
>  (checkIE = document.createElement("b")).innerHTML = "<!--[if IE 9]><i></i><![endif]-->"; 
>  var isIE = checkIE.getElementsByTagName("i").length == 1;
>  
>  /\* IE 10 \*/
>  var isIE = eval('/*@cc_on!@*/false') && document.documentMode === 10;
>  
>  /\* IE10 \*/
>  var isIE = document.body.style.msTouchAction != undefined;
>  
>  上面列出的各个浏览器下Hack的写法，当然在实际运用之中并不建议使用Hack。
>  如果你的页面需要Hack来处理时，请先检查你的CSS和JS，如果实在无法达到要求，在考虑使用Hack来处理。
>
文章转自[大漠-主流浏览器的Hack写法](http://www.w3cplus.com/css/browser-hacks.html "点击阅读原文")