---
title: DataColumn 元素 （DataColumns_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 92469c2f-f809-dff2-d0ee-b3b8f75083d2
description: 定义在 Visio 用户界面中的外部数据窗口中的数据列的显示方式，并通过定义其数据类型和格式限定列中的数据。
ms.openlocfilehash: 453ff44131575bd3d6927fdddb81db5f3f431a3b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395845"
---
# <a name="datacolumn-element-datacolumnstype-complextype-visio-xml"></a>DataColumn 元素 （DataColumns_Type 复杂类型） (Visio XML)

定义在 Visio 用户界面中的**外部数据**窗口中的数据列的显示方式，并通过定义其数据类型和格式限定列中的数据。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[DataColumn_Type](datacolumn_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |recordsets.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="DataColumn" type="DataColumn_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataColumns](datacolumns-element-datarecordset_type-complextypevisio-xml.md) <br/> |[DataColumns_Type](datacolumns_type-complextypevisio-xml.md) <br/> |包含数据记录集中的所有**DataColumn**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|日历  <br/> |xsd:unsignedShort  <br/> |可选  <br/> |日历数据列的 ID。  <br/> |Xsd:unsignedShort 类型的值。  <br/> |
|ColumnNameID  <br/> |xsd: string  <br/> |必需  <br/> |外部数据列的名称。 将显示在和中数据图形标签**外部数据**窗口中的标题。  <br/> |Xsd: string 类型的值。  <br/> |
|货币  <br/> |xsd:unsignedShort  <br/> |可选  <br/> |数据列的货币 ID。  <br/> |Xsd:unsignedShort 类型的值。  <br/> |
|DataType  <br/> |xsd:unsignedShort  <br/> |可选  <br/> |在数据列中的数据类型。  <br/> |Xsd:unsignedShort 类型的值。  <br/> |
|Degree  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |指定的单位，例如平方，或立方 （电源） 程度。 默认值 （属性不存在） 为 1。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|DisplayOrder  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |在**外部数据**窗口中，从最左侧的列 (0) 到最右侧的列 （最大值） 定义的数据列的显示位置。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|DisplayWidth  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |在**外部数据**窗口中的数据列的宽度。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|超链接  <br/> |化  <br/> |可选  <br/> |是否数据列时，创建一个超链接形状中形状链接到数据。  <br/> |化类型的值。  <br/> |
|标签  <br/> |xsd: string  <br/> |必需  <br/> |数据列的标签。  <br/> |Xsd: string 类型的值。  <br/> |
|LangID  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |数据列的语言 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|映射  <br/> |化  <br/> |可选  <br/> |指定列在**外部数据**窗口中是否可见。 列可见，则为 true (1)False (0) 不要是可见的列。 默认值 （属性不存在） 为可见的列。  <br/> |化类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |必需  <br/> |数据列的内部名称。 用作时该形状链接到数据行添加到形状的形状数据项 （自定义属性） 行名称。  <br/> |Xsd: string 类型的值。  <br/> |
|OrigLabel  <br/> |xsd: string  <br/> |可选  <br/> |由基础 ADO 接口返回到 Visio 列标签。  <br/> |Xsd: string 类型的值。  <br/> |
|UnitType  <br/> |xsd: string  <br/> |可选  <br/> |单位中的数据列的数据类型。  <br/> |Xsd: string 类型的值。  <br/> |
   

