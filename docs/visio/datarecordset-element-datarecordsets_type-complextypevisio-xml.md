---
title: 'DataRecordSet 元素 (DataRecordSets_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: aa182f04-0899-ee0e-79e1-b74832933e83
description: 在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。
ms.openlocfilehash: e478593f370968db5fe9a65329cb1928c0f7c6ea
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539675"
---
# <a name="datarecordset-element-datarecordsets_type-complextype-visio-xml"></a>DataRecordSet 元素 (DataRecordSets_Type COMPLEXType)  (Visio XML) 

在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |recordsets.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="DataRecordSet" type="DataRecordSet_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataRecordSets](datarecordsets-elementvisio-xml.md) <br/> |[DataRecordSets_Type](datarecordsets_type-complextypevisio-xml.md) <br/> |包含文档中 **的所有 DataRecordset** 元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[ADOData](autolinkcomparison-element-datarecordset_type-complextypevisio-xml.md) <br/> |[ADOData_Type](autolinkcomparison_type-complextypevisio-xml.md) <br/> |包含符合 ADO 记录集的 ADO 经典 XML 架构并描述数据记录集数据的 XML。  <br/> |
|[AutoLinkComparison](autolinkcomparison-element-datarecordset_type-complextypevisio-xml.md) <br/> |[AutoLinkComparison_Type](autolinkcomparison_type-complextypevisio-xml.md) <br/> |定义一个规则，该规则将 **父 DataRecordset** 元素中的列与形状数据项与上次在用户界面中成功执行的自动链接操作进行比较。  <br/> |
|[DataColumn](datacolumns-element-datarecordset_type-complextypevisio-xml.md) <br/> |[DataColumns_Type](datacolumns_type-complextypevisio-xml.md) <br/> |定义数据列在 Visio 用户界面的"外部数据"窗口中的显示方式，并定义数据列的数据类型和格式。  <br/> |
|[DataColumns](datacolumns-element-datarecordset_type-complextypevisio-xml.md) <br/> |[DataColumns_Type](datacolumns_type-complextypevisio-xml.md) <br/> |包含数据记录集内的所有 **DataColumn** 元素。  <br/> |
|[PrimaryKey](primarykey-element-datarecordset_type-complextypevisio-xml.md) <br/> |[PrimaryKey_Type](primarykey_type-complextypevisio-xml.md) <br/> |标识数据记录集的一个或多个主键列。  <br/> |
|[RefreshConflict](refreshconflict-element-datarecordset_type-complextypevisio-xml.md) <br/> |[RefreshConflict_Type](refreshconflict_type-complextypevisio-xml.md) <br/> |指示数据记录集内链接到在刷新数据记录集后存在冲突的形状的行。  <br/> |
|[RowMap](rowmap-element-datarecordset_type-complextypevisio-xml.md) <br/> |[RowMap_Type](rowmap_type-complextypevisio-xml.md) <br/> |地图数据记录集行与形状。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|校验和  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |一个校验和值，由Visio数据记录集属性生成。 将 this attirbute 设置为 0;Visio在运行时重新计算此值。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|Command  <br/> |xsd：string  <br/> |可选  <br/> |用于查询数据源数据的命令字符串。  <br/> |xsd：string 类型的值。  <br/> |
|ConnectionID  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |关联的 **DataConnection** 对象的连接 ID。 XML 数据源不存在。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |数据记录集 ID，在文档中是唯一的。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd：string  <br/> |可选  <br/> |显示 (或"友好") 数据记录集的名称。  <br/> |xsd：string 类型的值。  <br/> |
|NextRowID  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |下一个可用的Visio行 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|选项  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |应用于数据记录集的选项。 可能的值可以是下表中显示的一个或多个值的任意组合。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|RefreshInterval  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |自动 (数据记录) Visio刷新频率（以分钟计算）。 此值必须为 1 或更大。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|RefreshNoReconciliationUI  <br/> |xsd：boolean  <br/> |可选  <br/> |是否应该禁用数据对帐用户界面。 真 (1) 禁用用户界面用户界面 (UI) 。 假 (0) 启用 UI。  <br/> |xsd：boolean 类型的值。  <br/> |
|RefreshOverwriteAll  <br/> |xsd：boolean  <br/> |可选  <br/> |刷新数据记录集时是否覆盖用户对链接到数据的形状中形状数据项的更改。  <br/> |xsd：boolean 类型的值。  <br/> |
|ReplaceLinks  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |定义在复制或剪切形状时如何处理形状数据链接。 1：替换目标形状中的现有链接。 0，以维护目标形状中的现有链接。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|RowOrder  <br/> |xsd：boolean  <br/> |可选  <br/> |是否使用数据记录集内行的顺序作为主键。 如此 (1) 行的行的行顺序。 假 (0) 行的行号由数据记录集的主键列中 () 值。  <br/> |xsd：boolean 类型的值。  <br/> |
|TimeRefreshed  <br/> |xsd：dateTime  <br/> |可选  <br/> |上次刷新数据记录集的日期和时间。  <br/> |xsd：dateTime 类型的值。  <br/> |
   

