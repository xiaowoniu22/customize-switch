# customize-switch
效果预览https://jsfiddle.net/xiaowoniu/5ds3x37r/62/
移动端H5开发中经常会用到switch开关，有很多UI库也都提供了switch开关。今天，闲来无事，我自己写了一个自定义开关，具体代码如下：
# html
<input type="checkbox" class="switch"/>


# css
.switch{
  appearance: none;
  -moz-appearance: none;
  -webkit-appearance: none;
  outline:0;
  width:62px;
  height:32px;
  border: 1px solid #39c2d3;
  border-radius: 16px;
  /* transition: background-color .1s, border .1s; */
  position:relative;
  &:before{
    content:'是';
    display:block;
    height:26px;
    width: 52px;
    line-height:26px;
    transition:transform .35s cubic-bezier(0.45, 1, 0.4, 1);
    text-align:right;
    position:absolute;
    top:2px;
    color:#39c2d3;
  }
  &:after{
    content:'否';
    display:block;
    width:26px;
    height:26px;
    line-height:26px;
    border:1px solid #39c2d3;
    border-radius: 14px;
    background-color: #39c2d3;
    color: #fff;
    text-align:center;
    transition:transform 0.35s cubic-bezier(0.4,0.4,0.25,1.35);
    position:absolute;
    top:1px;
    left:1px;
    
  }
}
.switch:checked{
  &:before{
    content:'否';
    text-align:left;
    transform: none;
    padding-left:8px;
  }
  &:after{
    content:'是';
    transform: translateX(30px);
  }
}
