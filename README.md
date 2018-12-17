# scss
scss的用法

1. 变量 所有的变量以$开头
$fontSize: 14px;

.div {
  font-size: $fontSize;
}

2. 变量嵌套在字符串中
$color: color;

.rounded {
  background-#{$color}: red;
}

3. 允许计算
body {
  padding: (32px / 2);
  margin: 10px + 20px;
}

4.嵌套元素，属性 以及&符号
div {
  h1 {
    color: red;
    border: {
      radius: 10px;
    }
  }
}

a {
  &:hover {
    color: red;
  }
}

5. 继承
.class1 {
  background-color: red;
}

.class2 {
  @extend .class1;
}

6. mixin

@mixin right {
  display: flex;
  justify-content: center;
}

使用@include 调用 mixin

div {
  @include right;
}

mixin 还可以带默认的参数
@mixin left($value: 20px) {
  padding-right: $value;
}

div {
  @include left(10px);
}

7. 条件语句
p {
  @if 1 + 1 == 2 { 
     padding: 10px 
  } @else {
     padding: 5px; 
  }
}

8. for循环, while, each
@for $i from 1 to 10 { // 包前不包尾数
  .border-#{$i} {
    border: #{$i}px solid #333;    
  }
}

$i: 10;

@while $i > 0 {
  .item-#{$i} {
    height: 2px * $i;
  }
  $i: $i - 2;
}

@each $ember in a, b, c, d {
  .#{$ember} {
    background-image: url('../../image/#{$ember}.png')
  }
}

9 函数

@function double($n) {
  @return $n * 2
}

#div {
  width: double(10px);
}

在线地址 https://www.sassmeister.com/
