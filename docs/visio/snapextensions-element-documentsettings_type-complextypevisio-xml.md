---
title: 'SnapExtensions 元素 (DocumentSettings_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d55b6676-125f-7cf1-509d-21dee548f5a1
description: 指定是启用还是禁用活动窗口的特定对齐扩展设置。
ms.openlocfilehash: 86ff7f32d6e12b2f0d7a8387d8e5b7ae9870b5fa
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540376"
---
# <a name="snapextensions-element-documentsettings_type-complextype-visio-xml"></a>SnapExtensions 元素 (DocumentSettings_Type complexType)  (Visio XML) 

指定是启用还是禁用活动窗口的特定对齐扩展设置。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[SnapExtensions_Type](snapextensions_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |document.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="SnapExtensions" type="SnapExtensions_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DocumentSettings](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[DocumentSettings_Type](documentsettings_type-complextypevisio-xml.md) <br/> |包含指定文档设置的元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>Attributes

无。
  
## <a name="remarks"></a>说明

**SnapExtensions** 元素的值可以是下表中值的总和。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |不与任何内容对齐。  <br/> |
|1  <br/> |贴靠对齐框扩展。  <br/> |
|2  <br/> |贴靠中心轴延长线。  <br/> |
|4   <br/> |贴靠曲线切线扩展。  <br/> |
|8   <br/> |贴靠终结点扩展。  <br/> |
|16   <br/> |贴靠到中间点扩展。  <br/> |
|32  <br/> |贴靠线性扩展。  <br/> |
|64  <br/> |贴靠曲线扩展。  <br/> |
|128  <br/> |贴靠端点垂直延长线。  <br/> |
|256  <br/> |贴靠到中点垂直扩展。  <br/> |
|512  <br/> |贴靠到端点水平扩展。  <br/> |
|1024  <br/> |贴靠端点垂直扩展。  <br/> |
|2048  <br/> |贴靠椭圆中心扩展。  <br/> |
|4096  <br/> |贴靠等角扩展。  <br/> |
   

