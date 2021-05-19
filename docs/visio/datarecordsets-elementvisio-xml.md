---
title: 'DataRecordSets 元素 (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c75b3233-9ac5-d29c-a658-d554e86e6be4
description: 包含文档中的所有 DataRecordset 元素。
ms.openlocfilehash: efa7d58eabc1b1192862dbbe090ddd5008947c1d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542441"
---
# <a name="datarecordsets-element-visio-xml"></a>DataRecordSets 元素 (Visio XML) 

包含文档中 **的所有 DataRecordset** 元素。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[DataRecordSets_Type](datarecordsets_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |recordsets.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="DataRecordSets" type="DataRecordSets_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

无。
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataRecordSet](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |包含文档中 **的所有 DataRecordset** 元素。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|ActiveRecordsetID  <br/> |xsd：unsignedInt  <br/> |可选  <br/> |关闭"外部数据"窗口中活动数据记录集的 ID，以便下次打开该窗口时可以还原它。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|DataWindowOrder  <br/> |xsd：string  <br/> |可选  <br/> |"外部数据"窗口选项卡上显示 **的数据记录集** 的顺序。 数据记录集的有序列表，用分号分隔。  <br/> |xsd：string 类型的值。  <br/> |
|NextID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |新数据记录集的下一个可用 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
   

