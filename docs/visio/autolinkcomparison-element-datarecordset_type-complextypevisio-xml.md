---
title: AutoLinkComparison 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: af5eb7fd-89c6-49bf-4e45-431b63d6cd6a
description: 定义一个规则, 该规则将父 DataRecordset 元素中的列与在用户界面中上次执行的成功自动链接操作的形状数据项进行比较。
ms.openlocfilehash: 474acc4c1d259621881ea498decfeaf18b69809e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338316"
---
# <a name="autolinkcomparison-element-datarecordsettype-complextype-visio-xml"></a>AutoLinkComparison 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")

定义一个规则, 该规则将父**DataRecordset**元素中的列与在用户界面中上次执行的成功自动链接操作的形状数据项进行比较。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[AutoLinkComparison_Type](autolinkcomparison_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |记录集 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="AutoLinkComparison" type="AutoLinkComparison_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataRecordSet](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |指定在绘图页中该 recordset 和形状之间的 recordset 和数据绑定。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|ColumnName  <br/> |xsd: string  <br/> |必需  <br/> |对应于 ADO recordset 中的列名称。  <br/> |xsd: string 类型的值。  <br/> |
|ContextType  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |指定要用于比较的组或形状的属性。 下表中显示了可能的值。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|ContextTypeLabel  <br/> |xsd: string  <br/> |可选  <br/> |如果 ContextType 值为2或 3, 则需要使用此属性来定义比较。 对于 ContextType = 2, ContextTypeLabel 必须是 shape 数据项标签, 如果**ContextType** = 3, 则 ContextTypeLabel 必须为本地行名称。  <br/> |xsd: string 类型的值。  <br/> |
   

