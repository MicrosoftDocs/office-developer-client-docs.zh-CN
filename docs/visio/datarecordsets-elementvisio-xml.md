---
title: DataRecordSets 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c75b3233-9ac5-d29c-a658-d554e86e6be4
description: 包含文档中的所有数据记录集元素。
ms.openlocfilehash: 205c4d963f111490698627040c190f322f2f36a1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780038"
---
# <a name="datarecordsets-element-visio-xml"></a>DataRecordSets 元素 (Visio XML)

包含文档中的所有**数据记录集**元素。 
  
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

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

无。
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[数据记录集](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |包含文档中的所有**数据记录集**元素。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|ActiveRecordsetID  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |打开**外部数据**窗口时该窗口将关闭，以便使其可以还原下次窗口中的活动数据记录集的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|DataWindowOrder  <br/> |xsd: string  <br/> |可选  <br/> |在**外部数据**窗口的选项卡上显示的数据记录集的顺序。 数据记录集 Id，并用分号分隔的一个已排序的列表。  <br/> |Xsd: string 类型的值。  <br/> |
|NextID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |下一个可用 ID 为新的数据记录集的。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
   

