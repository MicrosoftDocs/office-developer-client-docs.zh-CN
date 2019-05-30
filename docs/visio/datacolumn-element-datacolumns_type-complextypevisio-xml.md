---
title: DataColumn 元素 (DataColumns_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 92469c2f-f809-dff2-d0ee-b3b8f75083d2
description: 定义数据列在 Visio 用户界面的外部数据窗口中的显示方式, 并通过定义数据类型和格式来限定列中的数据。
ms.openlocfilehash: 021e7ffd154f1e124b9eb163acc27260b90c23eb
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541223"
---
# <a name="datacolumn-element-datacolumnstype-complextype-visio-xml"></a>DataColumn 元素 (DataColumns_Type 复杂类型) (Visio XML)

定义数据列在 Visio 用户界面的**外部数据**窗口中的显示方式, 并通过定义数据类型和格式来限定列中的数据。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[DataColumn_Type](datacolumn_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |记录集 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="DataColumn" type="DataColumn_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataColumns](datacolumns-element-datarecordset_type-complextypevisio-xml.md) <br/> |[DataColumns_Type](datacolumns_type-complextypevisio-xml.md) <br/> |包含数据记录集中的所有**DataColumn**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|日历  <br/> |xsd: unsignedShort  <br/> |可选  <br/> |数据列的日历 ID。  <br/> |Xsd: unsignedShort 类型的值。  <br/> |
|ColumnNameID  <br/> |xsd: string  <br/> |必需  <br/> |数据列的外部名称。 显示在 "**外部数据**" 窗口中的标题和数据图形的标签中。  <br/> |Xsd: string 类型的值。  <br/> |
|货币  <br/> |xsd: unsignedShort  <br/> |可选  <br/> |数据列的货币 ID。  <br/> |Xsd: unsignedShort 类型的值。  <br/> |
|DataType  <br/> |xsd: unsignedShort  <br/> |可选  <br/> |数据列中的数据类型。  <br/> |Xsd: unsignedShort 类型的值。  <br/> |
|Degree  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |指定单位的度数 (功率), 例如, 平方或立方。 默认值 (属性不存在) 为1。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|DisplayOrder  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |定义数据列在**外部数据**窗口中的显示位置, 从最左侧的列 (0) 到最右侧的列 (最大值)。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|DisplayWidth  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |"**外部数据**" 窗口中的数据列的宽度。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|超链接  <br/> |xsd: boolean  <br/> |可选  <br/> |当形状链接到数据时, 数据列是否在形状中创建超链接。  <br/> |Xsd: boolean 类型的值。  <br/> |
|标签  <br/> |xsd: string  <br/> |必需  <br/> |数据列的标签。  <br/> |Xsd: string 类型的值。  <br/> |
|LangID  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |数据列的语言 ID。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|分区  <br/> |xsd: boolean  <br/> |可选  <br/> |指定列在 "**外部数据**" 窗口中是否可见。 如果为 True (1), 则列可见;如果为 False (0), 则该列将不可见。 默认值 (属性不存在) 是列的可见性。  <br/> |Xsd: boolean 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |必需  <br/> |数据列的内部名称。 当形状链接到数据行时, 用作形状数据项 (自定义属性) 的行名称添加到形状中的项。  <br/> |Xsd: string 类型的值。  <br/> |
|OrigLabel  <br/> |xsd: string  <br/> |可选  <br/> |由基础 ADO 接口返回到 Visio 的列标签。  <br/> |Xsd: string 类型的值。  <br/> |
|UnitType  <br/> |xsd: string  <br/> |可选  <br/> |数据列中数据的单位类型。  <br/> |Xsd: string 类型的值。  <br/> |
   

