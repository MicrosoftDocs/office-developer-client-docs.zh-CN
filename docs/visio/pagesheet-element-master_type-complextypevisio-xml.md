---
title: PageSheet 元素 （Master_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 824fbeb0-1a2f-35a0-50e3-c57143dc21ab
description: 指定绘图页主控形状相关联的属性。
ms.openlocfilehash: ab20cfe4561cd5fd0eeb6edad0b3a608428b0e8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780877"
---
# <a name="pagesheet-element-mastertype-complextype-visio-xml"></a>PageSheet 元素 （Master_Type 复杂类型） (Visio XML)

指定绘图页主控形状相关联的属性。
  
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

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Master](master-element-masters_type-complextypevisio-xml.md) <br/> |[Master_Type](master_type-complextypevisio-xml.md) <br/> |指定与绘图中的主控形状。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|FillStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定从中继承填充格式的样式表的 ID。 它必须与绘图中**StyleSheet_Type**相关联的**ID**属性的值。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|LineStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定从中继承线条格式样式表的 ID。 它必须与绘图中**StyleSheet_Type**相关联的**ID**属性的值。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|TextStyle  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定从中继承文本格式的样式表的 ID。 它必须与绘图中**StyleSheet_Type**相关联的**ID**属性的值。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|UniqueID  <br/> |xsd: string  <br/> |可选  <br/> |其父元素中的元素的唯一 ID。  <br/> |Xsd: string 类型的值。  <br/> |
   

