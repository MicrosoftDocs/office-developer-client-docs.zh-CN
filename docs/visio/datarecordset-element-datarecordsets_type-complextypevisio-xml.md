---
title: DataRecordSet 元素 （DataRecordSets_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: aa182f04-0899-ee0e-79e1-b74832933e83
description: 在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。
ms.openlocfilehash: 157213476214c736367b724dd6ca944060c53467
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780039"
---
# <a name="datarecordset-element-datarecordsetstype-complextype-visio-xml"></a>DataRecordSet 元素 （DataRecordSets_Type 复杂类型） (Visio XML)

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

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataRecordSets](datarecordsets-elementvisio-xml.md) <br/> |[DataRecordSets_Type](datarecordsets_type-complextypevisio-xml.md) <br/> |包含文档中的所有**数据记录集**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[ADOData](autolinkcomparison-element-datarecordset_type-complextypevisio-xml.md) <br/> |[ADOData_Type](autolinkcomparison_type-complextypevisio-xml.md) <br/> |包含符合 ADO 记录集的 ADO 经典 XML 架构，并且描述的数据记录集中的数据的 XML。  <br/> |
|[AutoLinkComparison](autolinkcomparison-element-datarecordset_type-complextypevisio-xml.md) <br/> |[AutoLinkComparison_Type](autolinkcomparison_type-complextypevisio-xml.md) <br/> |定义一个将形状数据项目从上次成功自动链接执行的操作在用户界面中将父**DataRecordset**元素中的列进行比较的规则。  <br/> |
|[DataColumn](datacolumns-element-datarecordset_type-complextypevisio-xml.md) <br/> |[DataColumns_Type](datacolumns_type-complextypevisio-xml.md) <br/> |定义在 Visio 用户界面中的**外部数据**窗口中的数据列的显示方式，并通过定义其数据类型和格式限定列中的数据。  <br/> |
|[DataColumns](datacolumns-element-datarecordset_type-complextypevisio-xml.md) <br/> |[DataColumns_Type](datacolumns_type-complextypevisio-xml.md) <br/> |包含数据记录集中的所有**DataColumn**元素。  <br/> |
|[PrimaryKey](primarykey-element-datarecordset_type-complextypevisio-xml.md) <br/> |[PrimaryKey_Type](primarykey_type-complextypevisio-xml.md) <br/> |标识数据记录集中的一个或多个主键列。  <br/> |
|[RefreshConflict](refreshconflict-element-datarecordset_type-complextypevisio-xml.md) <br/> |[RefreshConflict_Type](refreshconflict_type-complextypevisio-xml.md) <br/> |指示链接到形状的数据记录集刷新后存在冲突的数据记录集中的行。  <br/> |
|[RowMap](rowmap-element-datarecordset_type-complextypevisio-xml.md) <br/> |[RowMap_Type](rowmap_type-complextypevisio-xml.md) <br/> |映射到形状的数据记录集行。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|校验和  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |一个校验和值由 Visio，生成和基于数据记录集属性。 将此 attirbute 设置为 0;Visio 将此值在运行时进行重新计算。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|命令  <br/> |xsd: string  <br/> |可选  <br/> |从数据源查询数据使用的命令字符串。  <br/> |Xsd: string 类型的值。  <br/> |
|ConnectionID  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |关联的**DataConnection**对象的连接 ID。 不存在的 XML 数据源。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |数据记录集 ID，唯一的文档中。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |显示 （或"友好"） 的数据记录集的名称。  <br/> |Xsd: string 类型的值。  <br/> |
|NextRowID  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |下一个可用 Visio 行 id。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|选项  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |要应用于的数据记录集的选项。 可能的值可以是任意组合的一个或多个下表中所示。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|RefreshInterval  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |频率 （以分钟为单位） Visio 自动刷新数据记录集。 该值必须是 1 或更大。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|RefreshNoReconciliationUI  <br/> |化  <br/> |可选  <br/> |是否应禁用数据调节用户界面。 True (1) 若要禁用的用户界面 (UI)。 False (0)，以启用 UI。  <br/> |化类型的值。  <br/> |
|RefreshOverwriteAll  <br/> |化  <br/> |可选  <br/> |刷新数据记录集时是否覆盖用户更改形状中的形状数据项目链接到数据。  <br/> |化类型的值。  <br/> |
|ReplaceLinks  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |定义形状数据链接复制或剪切形状时的处理方式。 若要替换现有的链接的目标形状中的 1。 维护现有的链接的目标形状中的 0。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|RowOrder  <br/> |化  <br/> |可选  <br/> |是否为主键使用中的数据记录集的行的顺序。 如果行 Id 由行顺序，则 true (1)。 False (0)，如果行 Id 由中的数据记录集主键列的值。  <br/> |化类型的值。  <br/> |
|TimeRefreshed  <br/> |化  <br/> |可选  <br/> |日期和时间上次刷新数据记录集。  <br/> |化类型的值。  <br/> |
   

