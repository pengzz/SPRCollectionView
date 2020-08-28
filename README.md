# ios-spring-shrink-move-expand-collectionView 

[![Support](https://img.shields.io/badge/platform-iOS8%2B-blue.svg?style=flat)](https://www.apple.com/nl/ios/)&nbsp;

iOS:使用CollectionView实现Wallet效果 

## 实现的效果

![](https://github.com/TactBoy/ios-spring-shrink-move-expand-collectionView/raw/master/效果.gif)     

## 已知缺陷
* 与`collectionView`顶端的`Cell`交换时,动画会不流畅,可能原因是`cell`执行交换动画时,不能正常加载即将要显示的`cell`,这个是由于`cell`置顶导致的.

    注释掉这行代码,效果就会很明显:
    
     ```
        if (self.isMoveing) {
          return;
        }
     ```
     
* 点击`cell`打开时,其他`cell`收起来的动画会很突兀

**如果有什么好的解决方案, 欢迎提交pull request, 或者来[简书](http://www.jianshu.com/p/b0fa1daa8665)一起讨论**



## ZZ修改版
**修改完善内容**
* 长按滑动移动卡片问题：1.最顶和最下移动不替换的问题解决。2.滑动到顶到底时由于inset的存在，移动卡片时collectionview滑动到的位置不对的问题。3.inset纠正，即collectionView的inset与itemSize大小的纠正，与代码里涉及cell宽度的修正。
* 点击卡片展开：1.展开后向下慢速拖动动松手后所有卡片大小、位置、动画调整（一些卡片向左移）。2.cellectionView滑动到后面点击cell展开时点击关闭或者拖动关闭时当前cell直接向上漂向顶方。3.展开的当前cell,点击关闭时动画与层级关系的纠正。
* 大约就如上一些吧。
