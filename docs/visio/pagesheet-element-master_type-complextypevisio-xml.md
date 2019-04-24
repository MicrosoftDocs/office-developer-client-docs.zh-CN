---
title: PageSheet 元素 (Master_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 824fbeb0-1a2f-35a0-50e3-c57143dc21ab
description: 指定与主控形状相关联的绘图页的属性。
ms.openlocfilehash: 579b2b4f02c79a38842a150b8757329e19e7bb3a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361122"
---
# <a name="pagesheet-element-mastertype-complextype-visio-xml"></a>PageSheet 元素 (Master_Type 复杂类型) ("Visio XML")

指定与主控形状相关联的绘图页的属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |主控 xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="PageSheet" type="PageSheet_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Master](master-element-masters_type-complextypevisio-xml.md) <br/> |[Master_Type](master_type-complextypevisio-xml.md) <br/> |指定绘图中的主控形状。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|FillStyle  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |指定要从中继承填充格式的样式表的 ID。 它必须是与绘图中的**StyleSheet_Type**相关联的**ID**属性的值。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|LineStyle  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |指定要从中继承行格式设置的样式表的 ID。 它必须是与绘图中的**StyleSheet_Type**相关联的**ID**属性的值。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|TextStyle  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |指定要从中继承文本格式设置的样式表的 ID。 它必须是与绘图中的**StyleSheet_Type**相关联的**ID**属性的值。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|UniqueID  <br/> |xsd: string  <br/> |可选  <br/> |元素在其父元素中的唯一 ID。  <br/> |xsd: string 类型的值。  <br/> |
   

