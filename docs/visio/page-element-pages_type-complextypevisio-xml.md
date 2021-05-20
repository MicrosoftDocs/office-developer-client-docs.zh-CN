---
title: 'Page 元素 (Pages_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6e4ac41f-3855-05d8-e659-02c265b8750c
description: 包含定义文档中页面的元素。
ms.openlocfilehash: f32cf3ed7bbf1e68ddca3fc8f5a1c50ce45fe73e
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538023"
---
# <a name="page-element-pages_type-complextype-visio-xml"></a>Page 元素 (Pages_Type complexType)  (Visio XML) 

包含定义文档中页面的元素。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Page_Type](page_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |pages.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Page" type="Page_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Pages](pages-elementvisio-xml.md) <br/> |[Pages_Type](pages_type-complextypevisio-xml.md) <br/> |包含 **文档的 Page** 元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[PageSheet](pagesheet-element-page_type-complextypevisio-xml.md) <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |包含定义 Page 元素的页面 **工作表** 的元素。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|背景  <br/> |xsd：boolean  <br/> |可选  <br/> |一个标志，指示页面是否为背景页。  <br/> |xsd：boolean 类型的值。  <br/> |
|BackPage  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |此页面的背景页的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |元素在其父元素中的唯一 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|IsCustomName  <br/> |xsd：boolean  <br/> |可选  <br/> |指示用户是否已自定义该名称。  <br/> |xsd：Boolean 类型的值。  <br/> |
|IsCustomNameU  <br/> |xsd：boolean  <br/> |可选  <br/> |指示用户是否已自定义通用名称。  <br/> |xsd：Boolean 类型的值。  <br/> |
|名称  <br/> |xsd：string  <br/> |可选  <br/> |元素的名称。  <br/> |xsd：string 类型的值。  <br/> |
|NameU  <br/> |xsd：string  <br/> |可选  <br/> |元素的通用名称。  <br/> |xsd：string 类型的值。  <br/> |
|ReviewerID  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |与标记贴关联的审阅者的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|ViewCenterX  <br/> |xsd：double  <br/> |可选  <br/> |**ViewCenterX** 和 **ViewCenterY** 在页面上指定一个中心点，新视图 (窗口) 最初打开时假定该位置。  <br/> |xsd：double 类型的值。  <br/> |
|ViewCenterY  <br/> |xsd：double  <br/> |可选  <br/> |**ViewCenterX** 和 **ViewCenterY** 在页面上指定一个中心点，新视图 (窗口) 最初打开时假定该位置。  <br/> |xsd：double 类型的值。  <br/> |
|ViewScale  <br/> |xsd：double  <br/> |可选  <br/> |打开页面的新视图窗口窗口 (时) 的默认放大系数。 例如，1 = 100？1.5 = 150%，等等。  <br/> |xsd：double 类型的值。  <br/> |
   

