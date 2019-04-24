---
title: Rel 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9148c73f-970d-61f8-b5da-e3bc748a6541
description: 使用关联的 recordset 和数据绑定信息指定与部件的关系。
ms.openlocfilehash: ca3584cfa8f1791e126d867a541de1fe9ec4b354
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360156"
---
# <a name="rel-element-datarecordsettype-complextype-visio-xml"></a>Rel 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")

使用关联的 recordset 和数据绑定信息指定与部件的关系。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Rel_Type](rel_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |pages. .xml、xml、recordset、.xml、第 .xml、master # .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Rel" type="Rel_Type" minOccurs="1" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataRecordSet](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |指定存储在绘图中的 recordset 和数据绑定信息的一个实例。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|r:id  <br/> |xsd: string  <br/> 请参阅注解。  <br/> |必需  <br/> |指定与部件的关系。  <br/> |"rId #"  <br/> 请参阅注解。  <br/> |
   
## <a name="remarks"></a>注解

**r:id**属性的值必须是**ST_RelationshipID**类型。 **ST_RelationshipID**类型是一个必须采用 "rId #" 格式的字符串, 其中最后一个字符必须是数字。 该数字在**Rel**元素的所有同辈元素中必须是唯一的。 
  
有关 ST_RelationshipID 类型的详细信息, 请参阅[ISO/IEC 29500 第1部分规范](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750)。
  

