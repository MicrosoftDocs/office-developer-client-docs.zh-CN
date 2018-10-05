---
title: 网页元素 （Pages_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6e4ac41f-3855-05d8-e659-02c265b8750c
description: 包含文档中定义的网页的元素。
ms.openlocfilehash: 800e4ab2c6446ab298747f0492800000bb44cca3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398006"
---
# <a name="page-element-pagestype-complextype-visio-xml"></a>网页元素 （Pages_Type 复杂类型） (Visio XML)

包含文档中定义的网页的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Page_Type](page_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |pages.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Page" type="Page_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Pages](pages-elementvisio-xml.md) <br/> |[Pages_Type](pages_type-complextypevisio-xml.md) <br/> |包含文档的**页面**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[PageSheet](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |包含定义**页面**元素的页表的元素。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|背景  <br/> |化  <br/> |可选  <br/> |一个标志，指示页背景页。  <br/> |化类型的值。  <br/> |
|BackPage  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |此页面的背景页的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |其父元素中的元素的唯一 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|IsCustomName  <br/> |化  <br/> |可选  <br/> |指示是否由用户自定义名称。  <br/> |化类型的值。  <br/> |
|IsCustomNameU  <br/> |化  <br/> |可选  <br/> |指示是否由用户自定义的通用名称。  <br/> |化类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |元素的名称。  <br/> |Xsd: string 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |可选  <br/> |元素的通用名称。  <br/> |Xsd: string 类型的值。  <br/> |
|ReviewerID  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |审阅者标记贴相关联的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ViewCenterX  <br/> |化  <br/> |可选  <br/> |**ViewCenterX**和**ViewCenterY**指定的新视图 （窗口） 假定最初打开时页面上的中心点。  <br/> |化类型的值。  <br/> |
|ViewCenterY  <br/> |化  <br/> |可选  <br/> |**ViewCenterX**和**ViewCenterY**指定的新视图 （窗口） 假定最初打开时页面上的中心点。  <br/> |化类型的值。  <br/> |
|ViewScale  <br/> |化  <br/> |可选  <br/> |要打开页上的新视图 （窗口） 时使用的默认显示比例系数。 例如，1 = 100%。1.5 = 150%，依此类推。  <br/> |化类型的值。  <br/> |
   

