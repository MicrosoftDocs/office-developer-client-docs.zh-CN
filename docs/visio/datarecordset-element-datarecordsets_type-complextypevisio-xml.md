---
title: DataRecordSet 元素 (DataRecordSets_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: aa182f04-0899-ee0e-79e1-b74832933e83
description: 在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。
ms.openlocfilehash: e2baaeed38318f35d4bd4ce4269f71b6304b148f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360366"
---
# <a name="datarecordset-element-datarecordsetstype-complextype-visio-xml"></a>DataRecordSet 元素 (DataRecordSets_Type 复杂类型) ("Visio XML")

在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |记录集 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="DataRecordSet" type="DataRecordSet_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataRecordSets](datarecordsets-elementvisio-xml.md) <br/> |[DataRecordSets_Type](datarecordsets_type-complextypevisio-xml.md) <br/> |包含文档中的所有**DataRecordset**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[ADOData](autolinkcomparison-element-datarecordset_type-complextypevisio-xml.md) <br/> |[ADOData_Type](autolinkcomparison_type-complextypevisio-xml.md) <br/> |包含符合 ado 记录集的 ado 经典 XML 架构并描述数据记录集中的数据的 XML。  <br/> |
|[AutoLinkComparison](autolinkcomparison-element-datarecordset_type-complextypevisio-xml.md) <br/> |[AutoLinkComparison_Type](autolinkcomparison_type-complextypevisio-xml.md) <br/> |定义一个规则, 该规则将父**DataRecordset**元素中的列与在用户界面中上次执行的成功自动链接操作的形状数据项进行比较。  <br/> |
|[DataColumn](datacolumns-element-datarecordset_type-complextypevisio-xml.md) <br/> |[DataColumns_Type](datacolumns_type-complextypevisio-xml.md) <br/> |定义数据列在 Visio 用户界面的**外部数据**窗口中的显示方式, 并通过定义数据类型和格式来限定列中的数据。  <br/> |
|[DataColumns](datacolumns-element-datarecordset_type-complextypevisio-xml.md) <br/> |[DataColumns_Type](datacolumns_type-complextypevisio-xml.md) <br/> |包含数据记录集中的所有**DataColumn**元素。  <br/> |
|[关键字](primarykey-element-datarecordset_type-complextypevisio-xml.md) <br/> |[PrimaryKey_Type](primarykey_type-complextypevisio-xml.md) <br/> |标识数据记录集中的一个或多个主关键字列。  <br/> |
|[RefreshConflict](refreshconflict-element-datarecordset_type-complextypevisio-xml.md) <br/> |[RefreshConflict_Type](refreshconflict_type-complextypevisio-xml.md) <br/> |指示数据记录集中的行链接到的形状在数据记录集刷新后发生冲突。  <br/> |
|[RowMap](rowmap-element-datarecordset_type-complextypevisio-xml.md) <br/> |[RowMap_Type](rowmap_type-complextypevisio-xml.md) <br/> |将数据记录集行映射到形状。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|校验和  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |由 Visio 生成并基于数据记录集属性的校验和值。 将此 attirbute 设置为 0;Visio 会在运行时重新计算此值。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|Command  <br/> |xsd: string  <br/> |可选  <br/> |用于查询数据源中的数据的命令字符串。  <br/> |xsd: string 类型的值。  <br/> |
|ConnectionID  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |关联的**DataConnection**对象的连接 ID。 对于 XML 数据源, 不存在。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |数据记录集 ID, 在文档中是唯一的。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |数据记录集的显示 (或 "友好") 名称。  <br/> |xsd: string 类型的值。  <br/> |
|NextRowID  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |下一个可用的 Visio 行 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|选项  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |应用于数据记录集的选项。 可能的值可以是下表中所示的一个或多个值的任意组合。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|RefreshInterval  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |Visio 自动刷新数据记录集的频率 (以分钟为单位)。 此值必须大于或等于1。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|RefreshNoReconciliationUI  <br/> |xsd: boolean  <br/> |可选  <br/> |是否应禁用数据对帐用户界面。 True (1) 以禁用用户界面 (UI)。 False (0) 以启用 UI。  <br/> |xsd: boolean 类型的值。  <br/> |
|RefreshOverwriteAll  <br/> |xsd: boolean  <br/> |可选  <br/> |在刷新数据记录集时是否覆盖链接到数据的形状中的形状数据项的用户更改。  <br/> |xsd: boolean 类型的值。  <br/> |
|ReplaceLinks  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |定义在复制或剪切形状时如何处理形状数据链接。 1替换目标形状中的现有链接。 0, 用于维护目标形状中的现有链接。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|RowOrder  <br/> |xsd: boolean  <br/> |可选  <br/> |是否将数据记录集中的行的顺序用作主键。 如果行 id 由行顺序确定, 则为 True (1)。 如果行 id 由数据记录集的主键列中的值确定, 则为 False (0)。  <br/> |xsd: boolean 类型的值。  <br/> |
|TimeRefreshed  <br/> |xsd: dateTime  <br/> |可选  <br/> |上次刷新数据记录集的日期和时间。  <br/> |xsd: dateTime 类型的值。  <br/> |
   

