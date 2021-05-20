---
title: '连接 XML (Connects_Type复杂类型)  (Visio元素) '
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
# <a name="connect-element-connects_type-complextype-visio-xml"></a>连接 XML (Connects_Type复杂类型)  (Visio元素) 

表示绘图中的两个形状间的连接，如组织结构图中的线和框。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Connect_Type](connect_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |page#.xml，master#.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Connect" type="Connect_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Connects](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[Connects_Type](connects_type-complextypevisio-xml.md) <br/> |包含一 **连接** 图形中两个形状之间的每个连接的一个属性元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|FromCell  <br/> |xsd：string  <br/> |可选  <br/> |从其中建立连接的单元格。  <br/> |xsd：string 类型的值。  <br/> |
|FromPart  <br/> |xsd：int  <br/> |可选  <br/> |从形状中产生连接的部分。  <br/> |xsd：int 类型的值。  <br/> |
|FromSheet  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |产生连接的形状的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|ToCell  <br/> |xsd：string  <br/> |可选  <br/> |建立连接的单元格。  <br/> |xsd：string 类型的值。  <br/> |
|ToPart  <br/> |xsd：int  <br/> |可选  <br/> |要连接到的形状部分。  <br/> |xsd：Int 类型的值。  <br/> |
|ToSheet  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |要建立一个或多个连接的形状的 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
   

