# 盒模型

> CSS 盒模型是 CSS 的基石，非常重要的一块内容。

## 盒模型基本概念

1. margin + border + padding + content
2. 标准模型： 计算内容宽度时 width = content width，高度计算相同。
3. IE 模型： 计算内容宽度时 width = content + padding + border。
4. box-sizing: border-box、content-box。 
5. __JS 获取盒模型的宽高。__
6. __边距重叠及 BFC。__

## JS 获取盒模型的宽高

- dom.style.width/height