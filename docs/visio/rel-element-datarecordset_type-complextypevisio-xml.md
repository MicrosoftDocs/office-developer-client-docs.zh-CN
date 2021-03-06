---
title: 'Rel 元素 (DataRecordSet_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9148c73f-970d-61f8-b5da-e3bc748a6541
description: 指定与关联的记录集和数据绑定信息的部件的关系。
ms.openlocfilehash: fa93a3cbc32b6929b159b958ef2a96eafacf204f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542861"
---
# <a name="rel-element-datarecordset_type-complextype-visio-xml"></a>Rel 元素 (DataRecordSet_Type COMPLEXType)  (Visio XML) 

指定与关联的记录集和数据绑定信息的部件的关系。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Rel_Type](rel_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |pages.xml、masters.xml、recordsets.xml、page#.xml、master#.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Rel" type="Rel_Type" minOccurs="1" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataRecordSet](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |指定记录集的一个实例以及绘图中存储的数据绑定信息。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|r：id  <br/> |xsd：string  <br/> 请参阅注解。  <br/> |必需  <br/> |指定与部件的关系。  <br/> |"rId#"  <br/> 请参阅注解。  <br/> |
   
## <a name="remarks"></a>备注

**r：id** 属性的值必须是 **一个ST_RelationshipID** 类型。 the **ST_RelationshipID** type is a string that must be in the format 'rId#'， where the final character must be a number. 该数字在 **Rel** 元素的所有同级元素中必须是唯一的。 
  
有关类型类型ST_RelationshipID，请参阅 [ISO/IEC 29500 第 1 部分规范](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750)。
  

