---
title: AutoLinkComparison 元素 （DataRecordSet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: af5eb7fd-89c6-49bf-4e45-431b63d6cd6a
description: 定义一个将形状数据项目从上次成功自动链接执行的操作在用户界面中将父 DataRecordset 元素中的列进行比较的规则。
ms.openlocfilehash: 38970a84676f769c36c9bdc3f8334652f7d9ec21
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779669"
---
# <a name="autolinkcomparison-element-datarecordsettype-complextype-visio-xml"></a>AutoLinkComparison 元素 （DataRecordSet_Type 复杂类型） (Visio XML)

定义一个将形状数据项目从上次成功自动链接执行的操作在用户界面中将父**DataRecordset**元素中的列进行比较的规则。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[AutoLinkComparison_Type](autolinkcomparison_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |recordsets.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
<xs:element name="AutoLinkComparison" type="AutoLinkComparison_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[数据记录集](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |在绘图页指定记录集和该记录集和形状之间的数据绑定。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|ColumnName  <br/> |xsd: string  <br/> |必需  <br/> |对应于 ADO recordset 中的列名称。  <br/> |Xsd: string 类型的值。  <br/> |
|ContextType  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |指定要用于比较的组或形状的属性。 可能值如下表所示。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ContextTypeLabel  <br/> |xsd: string  <br/> |可选  <br/> |如果 ContextType 值为 2 或 3，此属性需要定义比较。 为 ContextType = 2，ContextTypeLabel 必须是形状数据项目标签，并且如果**ContextType** = 3，ContextTypeLabel 必须是本地行名称。  <br/> |Xsd: string 类型的值。  <br/> |
   

