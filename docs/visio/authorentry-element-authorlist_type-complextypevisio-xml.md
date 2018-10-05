---
title: AuthorEntry 元素 （AuthorList_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21ca601b-27f0-b30b-a99e-56359bdf594c
description: 指定用于确定在绘图中批注的作者属性。
ms.openlocfilehash: 81e5121a953102c7d2e3a5383ae9bc775af4ba41
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386327"
---
# <a name="authorentry-element-authorlisttype-complextype-visio-xml"></a>AuthorEntry 元素 （AuthorList_Type 复杂类型） (Visio XML)

指定用于确定在绘图中批注的作者属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[AuthorEntry_Type](authorentry_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |comments.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="AuthorEntry" type="AuthorEntry_Type" minOccurs="0" maxOccurs="unbounded" >
< /xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[AuthorList](authorlist-element-comments_type-complextypevisio-xml.md) <br/> |[AuthorList_Type](authorlist_type-complextypevisio-xml.md) <br/> |指定与绘图中的作者。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |一个从 1 开始的值，标识作者。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|Initials  <br/> |xsd: string  <br/> |可选  <br/> |作者的首字母缩写。  <br/> |Xsd: string 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |作者的名称。  <br/> |Xsd: string 类型的值。  <br/> |
|ResolutionID  <br/> |xsd: string  <br/> |可选  <br/> |作者的唯一标识符。  <br/> |Xsd: string 类型的值。  <br/> |
   

