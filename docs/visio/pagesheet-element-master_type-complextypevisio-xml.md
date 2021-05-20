---
title: '使用 XML (Master_Type complexType)  (Visio PageSheet) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 824fbeb0-1a2f-35a0-50e3-c57143dc21ab
description: 指定与主控板关联的绘图页的属性。
ms.openlocfilehash: 94fde64b130c2a05c4bd70c97552fe4218171ce7
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540614"
---
# <a name="pagesheet-element-master_type-complextype-visio-xml"></a>使用 XML (Master_Type complexType)  (Visio PageSheet) 

指定与主控板关联的绘图页的属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |masters.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="PageSheet" type="PageSheet_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Master](master-element-masters_type-complextypevisio-xml.md) <br/> |[Master_Type](master_type-complextypevisio-xml.md) <br/> |指定绘图中的主控图形。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|FillStyle  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |指定从其继承填充格式的样式表的 ID。 它必须是与绘图中的属性关联的 **ID** **StyleSheet_Type** 的值。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|LineStyle  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |指定要从其继承线条格式的样式表的 ID。 它必须是与绘图中的属性关联的 **ID** **StyleSheet_Type** 的值。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|TextStyle  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |指定要从其继承文本格式的样式表的 ID。 它必须是与绘图中的属性关联的 **ID** **StyleSheet_Type** 的值。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|UniqueID  <br/> |xsd：string  <br/> |可选  <br/> |元素在其父元素中的唯一 ID。  <br/> |xsd：string 类型的值。  <br/> |
   

