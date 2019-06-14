# CSS3 效果

- CSS3 效果
    - door-open 开门大吉源码
    - seamless-scrolling 无缝滚动源码

## css3 flex 布局

兼容性问题

- Android 
    - 2.3 开始支持旧版本的`display: -webkit-flex`
    - 4.4 开始支持标准版本的`display: flex`

- IOS 
    - 6.1 开始支持旧版本的 `display: -webkit-flex`
    - 7.1 开始支持标准版本的`display: flex`

- PC
    - `IE10`开始支持，但是`IE10` 的是`-ms`形式的。

兼容性的写法：

```css
    .box {
        /* 新版本语法：chrome 21+ */
        display: -webkit-flex; 
        /* 新版本语法：Opear 12.1,Firefox 22+ */
        display: flex; 
        /* 老版本语法：safari,Android browser,older Webkit browsers */
        display: -webkit-box;
        /* 老版本语法: Firefox (buggy) */
        display: -moz-box;
        /* 混合版本语法：IE10 */
        display: -ms-flexbox;
    }

    .flex1 {
        /* Chrome */
        -webkit-flex: 1; 
        /* IE10 */
        -ms-flex: 1;
        /* Opear 12.1,Firefox 20+ */
        flex: 1;
        /* IOS6, Safari 3.1-6 */
        -webkit-box-flex: 1;
        /* Firefox 19- */
        -moz-box-flex: 1;
    }
```

浏览器兼容的`flex` 语法：
```css
    .flex1 {
    -webkit-flex: 1;        /* Chrome */
    -ms-flex: 1             /* IE 10 */
    flex: 1;                /* NEW, Spec - Opera 12.1, Firefox 20+ */
    -webkit-box-flex: 1     /* OLD - iOS 6-, Safari 3.1-6 */
    -moz-box-flex: 1;       /* OLD - Firefox 19- */
}
.box{
 
    display: -webkit-flex;  /* 新版本语法: Chrome 21+ */
    display: flex;          /* 新版本语法: Opera 12.1, Firefox 22+ */
    display: -webkit-box;   /* 老版本语法: Safari, iOS, Android browser, older WebKit browsers. */
    display: -moz-box;      /* 老版本语法: Firefox (buggy) */
    display: -ms-flexbox;   /* 混合版本语法: IE 10 */
 
}

.flex1 {
    -webkit-flex: 1;        /* Chrome */
    -ms-flex: 1             /* IE 10 */
    flex: 1;                /* NEW, Spec - Opera 12.1, Firefox 20+ */
    -webkit-box-flex: 1     /* OLD - iOS 6-, Safari 3.1-6 */
    -moz-box-flex: 1;       /* OLD - Firefox 19- */
}
.box{
 
    display: -webkit-flex;  /* 新版本语法: Chrome 21+ */
    display: flex;          /* 新版本语法: Opera 12.1, Firefox 22+ */
    display: -webkit-box;   /* 老版本语法: Safari, iOS, Android browser, older WebKit browsers. */
    display: -moz-box;      /* 老版本语法: Firefox (buggy) */
    display: -ms-flexbox;   /* 混合版本语法: IE 10 */
 
}
/* 子元素-平均分栏 */
.flex1 {
  -webkit-box-flex: 1;      /* OLD - iOS 6-, Safari 3.1-6 */
  -moz-box-flex: 1;         /* OLD - Firefox 19- */
  width: 20%;               /* For old syntax, otherwise collapses. */
  -webkit-flex: 1;          /* Chrome */
  -ms-flex: 1;              /* IE 10 */
  flex: 1;                  /* NEW, Spec - Opera 12.1, Firefox 20+ */
}
/* 父元素-横向排列（主轴） */
.flex-h {
  display: box;              /* OLD - Android 4.4- */
  display: -webkit-box;      /* OLD - iOS 6-, Safari 3.1-6 */
  display: -moz-box;         /* OLD - Firefox 19- (buggy but mostly works) */
  display: -ms-flexbox;      /* TWEENER - IE 10 */
  display: -webkit-flex;     /* NEW - Chrome */
  display: flex;             /* NEW, Spec - Opera 12.1, Firefox 20+ */
  /* 09版 */
  -webkit-box-orient: horizontal;
  /* 12版 */
  -webkit-flex-direction: row;
  -moz-flex-direction: row;
  -ms-flex-direction: row;
  -o-flex-direction: row;
  flex-direction: row;
}
/* 父元素-横向换行 */
.flex-hw {
  /* 09版 */
  /*-webkit-box-lines: multiple;*/
  /* 12版 */
  -webkit-flex-wrap: wrap;
  -moz-flex-wrap: wrap;
  -ms-flex-wrap: wrap;
  -o-flex-wrap: wrap;
  flex-wrap: wrap;
}
/* 父元素-水平居中（主轴是横向才生效） */
.flex-hc {
  /* 09版 */
  -webkit-box-pack: center;
  /* 12版 */
  -webkit-justify-content: center;
  -moz-justify-content: center;
  -ms-justify-content: center;
  -o-justify-content: center;
  justify-content: center;
  /* 其它取值如下：
    align-items     主轴原点方向对齐
    flex-end        主轴延伸方向对齐
    space-between   等间距排列，首尾不留白
    space-around    等间距排列，首尾留白
   */
}
/* 父元素-纵向排列（主轴） */
.flex-v {
  display: box;              /* OLD - Android 4.4- */
  display: -webkit-box;      /* OLD - iOS 6-, Safari 3.1-6 */
  display: -moz-box;         /* OLD - Firefox 19- (buggy but mostly works) */
  display: -ms-flexbox;      /* TWEENER - IE 10 */
  display: -webkit-flex;     /* NEW - Chrome */
  display: flex;             /* NEW, Spec - Opera 12.1, Firefox 20+ */
  /* 09版 */
  -webkit-box-orient: vertical;
  /* 12版 */
  -webkit-flex-direction: column;
  -moz-flex-direction: column;
  -ms-flex-direction: column;
  -o-flex-direction: column;
  flex-direction: column;
}
/* 父元素-纵向换行 */
.flex-vw {
  /* 09版 */
  /*-webkit-box-lines: multiple;*/
  /* 12版 */
  -webkit-flex-wrap: wrap;
  -moz-flex-wrap: wrap;
  -ms-flex-wrap: wrap;
  -o-flex-wrap: wrap;
  flex-wrap: wrap;
}
/* 父元素-竖直居中（主轴是横向才生效） */
.flex-vc {
  /* 09版 */
  -webkit-box-align: center;
  /* 12版 */
  -webkit-align-items: center;
  -moz-align-items: center;
  -ms-align-items: center;
  -o-align-items: center;
  align-items: center;
}
/* 子元素-显示在从左向右（从上向下）第1个位置，用于改变源文档顺序显示 */
.flex-1 {
  -webkit-box-ordinal-group: 1;   /* OLD - iOS 6-, Safari 3.1-6 */
  -moz-box-ordinal-group: 1;      /* OLD - Firefox 19- */
  -ms-flex-order: 1;              /* TWEENER - IE 10 */
  -webkit-order: 1;               /* NEW - Chrome */
  order: 1;                       /* NEW, Spec - Opera 12.1, Firefox 20+ */
}
/* 子元素-显示在从左向右（从上向下）第2个位置，用于改变源文档顺序显示 */
.flex-2 {
  -webkit-box-ordinal-group: 2;   /* OLD - iOS 6-, Safari 3.1-6 */
  -moz-box-ordinal-group: 2;      /* OLD - Firefox 19- */
  -ms-flex-order: 2;              /* TWEENER - IE 10 */
  -webkit-order: 2;               /* NEW - Chrome */
  order: 2;                       /* NEW, Spec - Opera 12.1, Firefox 20+ */
}
```

## 移动端viewport 视口单位

1. 当把一个百分比的页面在移动设备浏览的时候，网页的宽度没有和设备宽度一致。
2. 移动设备的网页是基于什么？？？来计算宽度的？
3. 原因在移动设备中，浏览器和网页之间，还有一层虚拟的容器，这个容器叫 `viewport`
4. `viewport` 只有移动设备才有，而且主流设备当中的`viewport`默认宽度为980px，可以缩放

## 使用viewport 进行移动端的适配

标准化适配要求：
1. 网页的宽度和浏览器一致，网页的宽度和视口宽度一样，然后视口的宽度和浏览器一样（和设备的一样）
2. 保证网页内容的缩放比例和PC端保持一致，视口的缩放比是1:0；
3. 不允许用户自动缩放

去完成这个标准化的设置：
1. 怎么设置`viewport`
2. 具体的功能怎么实现

```css
<meta name="viewport" />
```

### 开门大吉源码
[door-open](https://github.com/yjn2015/CSS3)

1. 门关闭时的效果

![门关闭时的效果](https://github.com/yjn2015/CSS3/blob/master/door-open/door-close.png)

2. 门打开时的效果

![门打开时的效果](https://github.com/yjn2015/CSS3/blob/master/door-open/door-open.png)


