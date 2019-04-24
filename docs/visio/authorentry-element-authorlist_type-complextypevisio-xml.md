---
title: AuthorEntry 元素 (AuthorList_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21ca601b-27f0-b30b-a99e-56359bdf594c
description: 指定用于标识绘图中的注释作者的属性。
ms.openlocfilehash: 81e5121a953102c7d2e3a5383ae9bc775af4ba41
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338624"
---
# <a name="authorentry-element-authorlisttype-complextype-visio-xml"></a>AuthorEntry 元素 (AuthorList_Type 复杂类型) ("Visio XML")

指定用于标识绘图中的注释作者的属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[AuthorEntry_Type](authorentry_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |注释 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="AuthorEntry" type="AuthorEntry_Type" minOccurs="0" maxOccurs="unbounded" >
< /xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[AuthorList](authorlist-element-comments_type-complextypevisio-xml.md) <br/> |[AuthorList_Type](authorlist_type-complextypevisio-xml.md) <br/> |指定绘图中的作者。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|ID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |一个用于标识作者的基于1的值。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|缩写  <br/> |xsd: string  <br/> |可选  <br/> |作者的姓名首字母缩写。  <br/> |xsd: string 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |作者的姓名。  <br/> |xsd: string 类型的值。  <br/> |
|ResolutionID  <br/> |xsd: string  <br/> |可选  <br/> |作者的唯一标识符。  <br/> |xsd: string 类型的值。  <br/> |
   

