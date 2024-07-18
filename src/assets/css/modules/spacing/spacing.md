# 间距与尺寸

基础的尺寸与间距样式。

+ step:表示最小增量;
+ 按tiny、small、default、medium、large、huge递增。

## 宽度
<p class="w-step border">.w-step</p>
<p class="w-tiny border">.w-tiny</p>
<p class="w-small border">.w-small</p>
<p class="w-medium border">.w-medium</p>
<p class="w-large border">.w-large</p>
<p class="w-huge border">.w-huge</p>
<p class="w-default border">.w-default</p>

## 高度
.h-step
<p class="h-step border"></p>
<p class="h-small border">.h-small</p>
<p class="h-default border">.h-default</p>
<p class="h-medium border">.h-medium</p>
<p class="h-large border">.h-large</p>

## 间距
+ 相关属性值缩写对照:m-margin, p-padding, t-top, r-right, b-bottom, l-left, a-all, x-left and right, y-top and bottom。
<br>

```
.mt-step {
    margin-top: 5px!important
}

.mt-tiny {
    margin-top: 10px!important
}

.mt-small {
    margin-top: 15px!important
}

.mt-medium {
    margin-top: 20px!important
}

.mt-large {
    margin-top: 30px!important
}

.mt-huge {
    margin-top: 40px!important
}

.mt-0 {
    margin-top: 0!important
}

.mr-step {
    margin-right: 5px!important
}

.mr-tiny {
    margin-right: 10px!important
}

.mr-small {
    margin-right: 15px!important
}

.mr-medium {
    margin-right: 20px!important
}

.mr-large {
    margin-right: 30px!important
}

.mr-huge {
    margin-right: 40px!important
}

.mr-0 {
    margin-right: 0!important
}

.mb-step {
    margin-bottom: 5px!important
}

.mb-tiny {
    margin-bottom: 10px!important
}

.mb-small {
    margin-bottom: 15px!important
}

.mb-medium {
    margin-bottom: 20px!important
}

.mb-large {
    margin-bottom: 30px!important
}

.mb-huge {
    margin-bottom: 40px!important
}

.mb-0 {
    margin-bottom: 0!important
}

.ml-step {
    margin-left: 5px!important
}

.ml-tiny {
    margin-left: 10px!important
}

.ml-small {
    margin-left: 15px!important
}

.ml-medium {
    margin-left: 20px!important
}

.ml-large {
    margin-left: 30px!important
}

.ml-huge {
    margin-left: 40px!important
}

.ml-0 {
    margin-left: 0!important
}

.mx-step {
    margin-right: 5px!important;
    margin-left: 5px!important
}

.mx-tiny {
    margin-right: 10px!important;
    margin-left: 10px!important
}

.mx-small {
    margin-right: 15px!important;
    margin-left: 15px!important
}

.mx-medium {
    margin-right: 20px!important;
    margin-left: 20px!important
}

.mx-large {
    margin-right: 30px!important;
    margin-left: 30px!important
}

.mx-huge {
    margin-right: 40px!important;
    margin-left: 40px!important
}

.mx-0 {
    margin-right: 0!important;
    margin-left: 0!important
}

.my-step {
    margin-top: 5px!important;
    margin-bottom: 5px!important
}

.my-tiny {
    margin-top: 10px!important;
    margin-bottom: 10px!important
}

.my-small {
    margin-top: 15px!important;
    margin-bottom: 15px!important
}

.my-medium {
    margin-top: 20px!important;
    margin-bottom: 20px!important
}

.my-large {
    margin-top: 30px!important;
    margin-bottom: 30px!important
}

.my-huge {
    margin-top: 40px!important;
    margin-bottom: 40px!important
}

.my-0 {
    margin-top: 0!important;
    margin-bottom: 0!important
}

.m-step {
    margin: 5px!important
}

.m-tiny {
    margin: 10px!important
}

.m-small {
    margin: 15px!important
}

.m-medium {
    margin: 20px!important
}

.m-large {
    margin: 30px!important
}

.m-huge {
    margin: 40px!important
}

.m-0 {
    margin: 0!important
}

.pt-step {
    padding-top: 5px!important
}

.pt-tiny {
    padding-top: 10px!important
}

.pt-small {
    padding-top: 15px!important
}

.pt-medium {
    padding-top: 20px!important
}

.pt-large {
    padding-top: 30px!important
}

.pt-huge {
    padding-top: 40px!important
}

.pt-0 {
    padding-top: 0!important
}

.pr-step {
    padding-right: 5px!important
}

.pr-tiny {
    padding-right: 10px!important
}

.pr-small {
    padding-right: 15px!important
}

.pr-medium {
    padding-right: 20px!important
}

.pr-large {
    padding-right: 30px!important
}

.pr-huge {
    padding-right: 40px!important
}

.pr-0 {
    padding-right: 0!important
}

.pb-step {
    padding-bottom: 5px!important
}

.pb-tiny {
    padding-bottom: 10px!important
}

.pb-small {
    padding-bottom: 15px!important
}

.pb-medium {
    padding-bottom: 20px!important
}

.pb-large {
    padding-bottom: 30px!important
}

.pb-huge {
    padding-bottom: 40px!important
}

.pb-0 {
    padding-bottom: 0!important
}

.pl-step {
    padding-left: 5px!important
}

.pl-tiny {
    padding-left: 10px!important
}

.pl-small {
    padding-left: 15px!important
}

.pl-medium {
    padding-left: 20px!important
}

.pl-large {
    padding-left: 30px!important
}

.pl-huge {
    padding-left: 40px!important
}

.pl-0 {
    padding-left: 0!important
}

.px-step {
    padding-right: 5px!important;
    padding-left: 5px!important
}

.px-tiny {
    padding-right: 10px!important;
    padding-left: 10px!important
}

.px-small {
    padding-right: 15px!important;
    padding-left: 15px!important
}

.px-medium {
    padding-right: 20px!important;
    padding-left: 20px!important
}

.px-large {
    padding-right: 30px!important;
    padding-left: 30px!important
}

.px-huge {
    padding-right: 40px!important;
    padding-left: 40px!important
}

.px-0 {
    padding-right: 0!important;
    padding-left: 0!important
}

.py-step {
    padding-top: 5px!important;
    padding-bottom: 5px!important
}

.py-tiny {
    padding-top: 10px!important;
    padding-bottom: 10px!important
}

.py-small {
    padding-top: 15px!important;
    padding-bottom: 15px!important
}

.py-medium {
    padding-top: 20px!important;
    padding-bottom: 20px!important
}

.py-large {
    padding-top: 30px!important;
    padding-bottom: 30px!important
}

.py-huge {
    padding-top: 40px!important;
    padding-bottom: 40px!important
}

.py-0 {
    padding-top: 0!important;
    padding-bottom: 0!important
}

.p-step {
    padding: 5px!important
}

.p-tiny {
    padding: 10px!important
}

.p-small {
    padding: 15px!important
}

.p-medium {
    padding: 20px!important
}

.p-large {
    padding: 30px!important
}

.p-huge {
    padding: 40px!important
}

.p-0 {
    padding: 0!important
}
```

