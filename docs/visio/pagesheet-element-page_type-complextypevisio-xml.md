---
title: PageSheet 元素 （Page_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 99a6549b-099b-1546-cc30-db0010fe3ce1
description: 指定绘图页在绘图页相关联的属性。
ms.openlocfilehash: 8b60795c02717e4b752c09af19fa932f87924d1f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395131"
---
# <a name="pagesheet-element-pagetype-complextype-visio-xml"></a>PageSheet 元素 （Page_Type 复杂类型） (Visio XML)

指定绘图页在绘图页相关联的属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |pages.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="PageSheet" type="PageSheet_Type" minOccurs="0" maxOccurs="1" >
</xs:element > 
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[网页](page-element-pages_type-complextypevisio-xml.md) <br/> |[Page_Type](page_type-complextypevisio-xml.md) <br/> |包含文档中定义的网页的元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|FillStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定从中继承填充格式的样式表的 ID。 它必须与绘图中**StyleSheet_Type**相关联的**ID**属性的值。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|LineStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定从中继承线条格式样式表的 ID。 它必须与绘图中**StyleSheet_Type**相关联的**ID**属性的值。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|TextStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定从中继承文本格式的样式表的 ID。 它必须与绘图中**StyleSheet_Type**相关联的**ID**属性的值。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|UniqueID  <br/> |xsd: string  <br/> |可选  <br/> |其父元素中的元素的唯一 ID。  <br/> |Xsd: string 类型的值。  <br/> |
   

