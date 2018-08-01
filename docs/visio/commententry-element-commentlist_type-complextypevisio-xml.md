---
title: CommentEntry 元素 （CommentList_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b0653622-fa94-4889-68c2-94f3e7a83119
description: 指定用于标识与绘图中的注释的属性。
ms.openlocfilehash: b2ab1925c8b3b9a9c2d67ac48c1db1768f5916b2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779912"
---
# <a name="commententry-element-commentlisttype-complextype-visio-xml"></a>CommentEntry 元素 （CommentList_Type 复杂类型） (Visio XML)

指定用于标识与绘图中的注释的属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[CommentEntry_Type](commententry_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |comments.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="CommentEntry" type="CommentEntry_Type" minOccurs="0" maxOccurs="unbounded" >
< /xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[CommentList](commentlist-element-comments_type-complextypevisio-xml.md) <br/> |[CommentList_Type](commentlist_type-complextypevisio-xml.md) <br/> |指定与绘图中的注释。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|作者 Id  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |一个从 1 开始的值，标识作者。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|CommentID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |一个唯一值，该值标识绘图页中的注释。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|Date  <br/> |化  <br/> |必需  <br/> |指定何时创建批注。  <br/> |化类型的值。  <br/> |
|完成  <br/> |化  <br/> |可选  <br/> |指定批注的当前状态。  <br/> |化类型的值。  <br/> |
|EditDate  <br/> |化  <br/> |可选  <br/> |指定上次更改注释。  <br/> |化类型的值。  <br/> |
|PageID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |一个值，标识在绘图页上是注释。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ShapeID  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |一个值，标识形状上是注释。 如果未不指定任何 ShapeID，批注引用绘图页。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
   

