---
title: 'CommentEntry 元素 (CommentList_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b0653622-fa94-4889-68c2-94f3e7a83119
description: 指定用于标识绘图中的批注的属性。
ms.openlocfilehash: 6b4f20d632b54e7c96ef8181310e8ffab1abbd0f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540110"
---
# <a name="commententry-element-commentlist_type-complextype-visio-xml"></a>CommentEntry 元素 (CommentList_Type complexType)  (Visio XML) 

指定用于标识绘图中的批注的属性。
  
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

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[CommentList](commentlist-element-comments_type-complextypevisio-xml.md) <br/> |[CommentList_Type](commentlist_type-complextypevisio-xml.md) <br/> |指定绘图中的注释。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|AuthorID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |标识作者的从 1 到 1 的值。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|CommentID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |标识绘图页中的批注的唯一值。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|日期  <br/> |xsd：dateTime  <br/> |必需  <br/> |指定创建批注时。  <br/> |xsd：dateTime 类型的值。  <br/> |
|完成  <br/> |xsd：boolean  <br/> |可选  <br/> |指定批注的当前状态。  <br/> |xsd：boolean 类型的值。  <br/> |
|EditDate  <br/> |xsd：dateTime  <br/> |可选  <br/> |指定上次更改批注时。  <br/> |xsd：dateTime 类型的值。  <br/> |
|PageID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |一个值，该值标识批注所位于的绘图页。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|ShapeID  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |一个值，该值标识批注所基于的形状。 如果未指定 ShapeID，批注将引用绘图页。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
   

