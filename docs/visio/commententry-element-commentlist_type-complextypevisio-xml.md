---
title: CommentEntry 元素 (CommentList_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b0653622-fa94-4889-68c2-94f3e7a83119
description: 指定用于标识绘图中的注释的属性。
ms.openlocfilehash: 79d15b95f986826a4848c2dfbb003255d3482134
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329537"
---
# <a name="commententry-element-commentlisttype-complextype-visio-xml"></a>CommentEntry 元素 (CommentList_Type 复杂类型) ("Visio XML")

指定用于标识绘图中的注释的属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[CommentEntry_Type](commententry_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |注释 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="CommentEntry" type="CommentEntry_Type" minOccurs="0" maxOccurs="unbounded" >
< /xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[CommentList](commentlist-element-comments_type-complextypevisio-xml.md) <br/> |[CommentList_Type](commentlist_type-complextypevisio-xml.md) <br/> |指定绘图中的注释。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|AuthorID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |一个用于标识作者的基于1的值。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|CommentID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |标识绘图页中的注释的唯一值。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|日期  <br/> |xsd: dateTime  <br/> |必需  <br/> |指定何时创建注释。  <br/> |xsd: dateTime 类型的值。  <br/> |
|Done  <br/> |xsd: boolean  <br/> |可选  <br/> |指定注释的当前状态。  <br/> |xsd: boolean 类型的值。  <br/> |
|EditDate  <br/> |xsd: dateTime  <br/> |可选  <br/> |指定上次更改注释的时间。  <br/> |xsd: dateTime 类型的值。  <br/> |
|PageID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |一个值, 用于标识注释所在的绘图页。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|ShapeID  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |一个标识批注所在的形状的值。 如果未指定 ShapeID, 则注释引用绘图页。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
   

