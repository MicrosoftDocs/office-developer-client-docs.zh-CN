---
title: PageSheet 元素 (Page_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 99a6549b-099b-1546-cc30-db0010fe3ce1
description: 指定与绘图页相关联的绘图页的属性。
ms.openlocfilehash: 2f49d152a0fcb30e3f5aea98cdc251d3b65b8f69
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540621"
---
# <a name="pagesheet-element-pagetype-complextype-visio-xml"></a>PageSheet 元素 (Page_Type 复杂类型) (Visio XML)

指定与绘图页相关联的绘图页的属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[PageSheet_Type](pagesheet_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |pages  <br/> |
   
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
|[Page](page-element-pages_type-complextypevisio-xml.md) <br/> |[Page_Type](page_type-complextypevisio-xml.md) <br/> |包含用于定义文档中的页面的元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|FillStyle  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |指定要从中继承填充格式的样式表的 ID。 它必须是与绘图中的**StyleSheet_Type**相关联的**ID**属性的值。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|LineStyle  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |指定要从中继承行格式设置的样式表的 ID。 它必须是与绘图中的**StyleSheet_Type**相关联的**ID**属性的值。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|TextStyle  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |指定要从中继承文本格式设置的样式表的 ID。 它必须是与绘图中的**StyleSheet_Type**相关联的**ID**属性的值。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|UniqueID  <br/> |xsd: string  <br/> |可选  <br/> |元素在其父元素中的唯一 ID。  <br/> |Xsd: string 类型的值。  <br/> |
   

