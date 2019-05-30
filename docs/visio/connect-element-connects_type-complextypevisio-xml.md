---
title: Connect 元素 (Connects_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6e1ad47b-ee28-6b9a-f2f9-642e09ca28d4
description: 表示绘图中的两个形状间的连接，如组织结构图中的线和框。
ms.openlocfilehash: 3450a07e042fc633b9cd4952d9b3ad6b8190ed1e
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541993"
---
# <a name="connect-element-connectstype-complextype-visio-xml"></a>Connect 元素 (Connects_Type 复杂类型) (Visio XML)

表示绘图中的两个形状间的连接，如组织结构图中的线和框。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Connect_Type](connect_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |页面 # .xml、master # .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Connect" type="Connect_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Connects](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[Connects_Type](connects_type-complextypevisio-xml.md) <br/> |包含绘图中两个形状之间的每个连接的**Connect**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|FromCell  <br/> |xsd: string  <br/> |可选  <br/> |从中发起连接的单元格。  <br/> |Xsd: string 类型的值。  <br/> |
|FromPart  <br/> |xsd: int  <br/> |可选  <br/> |从其发起连接的形状的部件。  <br/> |Xsd: int 类型的值。  <br/> |
|FromSheet  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |从中发起连接或连接的形状的 ID。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|ToCell  <br/> |xsd: string  <br/> |可选  <br/> |建立了连接的单元格。  <br/> |Xsd: string 类型的值。  <br/> |
|ToPart  <br/> |xsd: int  <br/> |可选  <br/> |建立了连接的形状的一部分。  <br/> |Xsd: Int 类型的值。  <br/> |
|ToSheet  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |建立了一个或多个连接的形状的 ID。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
   

