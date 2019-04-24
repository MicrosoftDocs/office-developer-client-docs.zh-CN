---
title: Page 元素 (Pages_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6e4ac41f-3855-05d8-e659-02c265b8750c
description: 包含用于定义文档中的页面的元素。
ms.openlocfilehash: 800e4ab2c6446ab298747f0492800000bb44cca3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334445"
---
# <a name="page-element-pagestype-complextype-visio-xml"></a>Page 元素 (Pages_Type 复杂类型) ("Visio XML")

包含用于定义文档中的页面的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Page_Type](page_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |pages  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Page" type="Page_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Pages](pages-elementvisio-xml.md) <br/> |[Pages_Type](pages_type-complextypevisio-xml.md) <br/> |包含文档的**页面**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[PageSheet](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |包含用于定义**page**元素的页面表的元素。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|背景  <br/> |xsd: boolean  <br/> |可选  <br/> |指示页面是否为背景页面的标志。  <br/> |xsd: boolean 类型的值。  <br/> |
|BackPage  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |此页面的背景页面的 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |元素在其父元素中的唯一 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|IsCustomName  <br/> |xsd: boolean  <br/> |可选  <br/> |指示该名称是否已由用户自定义。  <br/> |xsd: Boolean 类型的值。  <br/> |
|IsCustomNameU  <br/> |xsd: boolean  <br/> |可选  <br/> |指示是否已由用户自定义通用名称。  <br/> |xsd: Boolean 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |元素的名称。  <br/> |xsd: string 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |可选  <br/> |元素的通用名称。  <br/> |xsd: string 类型的值。  <br/> |
|ReviewerID  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |与标记贴相关的审阅者的 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|ViewCenterX  <br/> |xsd: double  <br/> |可选  <br/> |**ViewCenterX**和**ViewCenterY**指定在最初打开时, 新视图 (窗口) 假定在页面上的中心点。  <br/> |xsd: double 类型的值。  <br/> |
|ViewCenterY  <br/> |xsd: double  <br/> |可选  <br/> |**ViewCenterX**和**ViewCenterY**指定在最初打开时, 新视图 (窗口) 假定在页面上的中心点。  <br/> |xsd: double 类型的值。  <br/> |
|ViewScale  <br/> |xsd: double  <br/> |可选  <br/> |打开页面的新视图 (窗口) 时使用的默认放大因子。 例如, 1 = 100%;1.5 = 150%, 依此类推。  <br/> |xsd: double 类型的值。  <br/> |
   

