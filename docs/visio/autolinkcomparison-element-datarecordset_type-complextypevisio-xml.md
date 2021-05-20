---
title: 'AutoLinkComparison 元素 (DataRecordSet_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: af5eb7fd-89c6-49bf-4e45-431b63d6cd6a
description: 定义一个规则，该规则将父 DataRecordset 元素中的列与形状数据项与上次在用户界面中成功执行的自动链接操作进行比较。
ms.openlocfilehash: 7d25d12844fe33ec1f1abb66984c5be40c4995c3
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537869"
---
# <a name="autolinkcomparison-element-datarecordset_type-complextype-visio-xml"></a>AutoLinkComparison 元素 (DataRecordSet_Type COMPLEXType)  (Visio XML) 

定义一个规则，该规则将 **父 DataRecordset** 元素中的列与形状数据项与上次在用户界面中成功执行的自动链接操作进行比较。 
  
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

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataRecordSet](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |指定记录集以及该记录集与绘图页中的形状之间的数据绑定。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|ColumnName  <br/> |xsd：string  <br/> |必需  <br/> |对应于 ADO 记录集的列名。  <br/> |xsd：string 类型的值。  <br/> |
|ContextType  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |指定要用于比较的组或形状的属性。 下表显示了可能的值。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|ContextTypeLabel  <br/> |xsd：string  <br/> |可选  <br/> |如果 ContextType 值为 2 或 3，则此属性是定义比较的必需属性。 对于 ContextType = 2，ContextTypeLabel 必须是形状数据项标签，如果 **ContextType** = 3，则 ContextTypeLabel 必须是本地行名称。  <br/> |xsd：string 类型的值。  <br/> |
   

