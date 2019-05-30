---
title: Cell 元素 (连接行) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7cafaa31-c56b-ebb0-3bfb-c339cc93038e
description: 包含形状上的单个连接点的 x 坐标或 y 坐标、水平或垂直方向或类型。
ms.openlocfilehash: 0c8177767d5c85d505ba8a2a430946fd29cf44aa
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541874"
---
# <a name="cell-element-connection-row-visio-xml"></a>Cell 元素 (连接行) (Visio XML)

包含形状上的单个连接点的 x 坐标或 y 坐标、水平或垂直方向或类型。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |master # .xml、第 .xml 页  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Row 元素 ("Connection" 内容)](row-element-connection-sectionvisio-xml.md) <br/> |[ConnectionRow_Type](connectionrow_type-complextypevisio-xml.md) <br/> |包含形状上单个连接点的 x 坐标和 y 坐标、水平和垂直方向以及类型。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |包含 x 坐标或 y 坐标、水平和垂直方向以及形状上的单个连接点的类型。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |xsd: string  <br/> |可选  <br/> |指示公式的计算结果为错误。 **E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。  <br/> |错误消息字符串。  <br/> |
|F  <br/> |xsd: string  <br/> |可选  <br/> | 代表元素的公式。 此属性可以包含以下字符串之一:  <br/>  "(某些公式)" 如果该公式在本地存在  <br/>  `No Formula`如果公式为本地删除或被阻止  <br/>  `Inh`如果公式是继承的。  <br/> |一个公式。  <br/> |
|N  <br/> |xsd: string  <br/> |必需  <br/> |代表 ShapeSheet 单元格的名称。  <br/> |ShapeSheet 单元格的名称。  <br/> 请参阅下面的 "备注" 部分。  <br/> |
|U  <br/> |xsd: string  <br/> |可选  <br/> |表示一个度量单位, 默认值为 DL。  <br/> |单元格的单位。  <br/> |
|部分  <br/> |xsd: string  <br/> |可选  <br/> |表示单元格的值。  <br/> |ShapeSheet 单元格的值。  <br/> |
   
## <a name="remarks"></a>备注

此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。 请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。 
  
|**值**|**说明**|**详细信息**|
|:-----|:-----|:-----|
|AutoGen  <br/> |指定是否自动生成连接点。 值为1表示自动生成连接点。  <br/> |无。  <br/> |
|DirX  <br/> |确定匹配连接点所需的对齐向量的 x 分量。  <br/> |[DirX / A Cell (Connection Points Section)](dirxa-cell-connection-points-section.md) <br/> |
|DirY  <br/> |确定匹配连接点所需的对齐向量的 y 分量。  <br/> |[DirY / B Cell (Connection Points Section)](diryb-cell-connection-points-section.md) <br/> |
|Prompt  <br/> |此属性留作将来使用。  <br/> |无。  <br/> |
|类型  <br/> |确定连接点类型。  <br/> |[Type / C Cell (Connection Points Section)](typec-cell-connection-points-section.md) <br/> |
|X  <br/> |表示连接点在本地坐标系中的 x 坐标。  <br/> |[X Cell (Connection Points Section)](x-cell-connection-points-section.md) <br/> |
|Y  <br/> |确定连接点在本地坐标系中的 y 坐标。  <br/> |[Y Cell (Connection Points Section)](y-cell-connection-points-section.md) <br/> |
   

