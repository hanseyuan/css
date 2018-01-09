### div+css 怎么让一个小div在另一个大div里面 垂直居中

#### 1.使用position定位
设置父元素div为相对定位.子元素div为绝对定位

    .parent {
              width:800px;
              height:500px;
              border:2px solid #000;
              position:relative;
    }
     .child {
                width:200px;
                height:200px;
                margin: auto;  
                position: absolute;  
                top: 0; left: 0; bottom: 0; right: 0; 
                background-color: red;
    }
#### 2.使用display:table-cell
display：table-cell 加上 vertical-align：middle 使高度不同的元素都垂直居中，其中div的display：inline-block使几个div在同一行显示。

table-cell元素的vertical-align为middle，它的内容的中点会对齐table-row元素的中点，并通过padding-top和padding-bottom设置相等的计算值，导致内容垂直居中。

        .parent {
            width:800px;
            height:500px;
            border:2px solid #000;
            display:table-cell;
            vertical-align:middle;
            text-align: center;
        }
        .child {
            width:200px;
            height:200px;
            display:inline-block;
            background-color: red;
        }
        
#### 3 display:flex;
justify-content 用于设置或检索弹性盒子元素在主轴（横轴）方向上的对齐方式。

align-items 属性定义flex子项在flex容器的当前行的侧轴（纵轴）方向上的对齐方式。

        .parent {
            width:800px;
            height:500px;
            border:2px solid #000;
            display:flex;
            justify-content:center; 
            align-items:center;
        }
        .child {
            width:200px;
            height:200px;
            background-color: red;
        }
4.定位计算

        .parent {
            width:800px;
            height:500px;
            border:2px solid #000;
            position:relative;
        }
        .child {
            width:300px;
            height:200px;
            margin:auto;
            position:absolute;/*设定水平和垂直偏移父元素的50%，再根据实际长度将子元素上左挪回一半大小*/
            left:50%;
            top:50%;
            margin-left: -150px;
            margin-top:-100px;
            background-color: red;
        }