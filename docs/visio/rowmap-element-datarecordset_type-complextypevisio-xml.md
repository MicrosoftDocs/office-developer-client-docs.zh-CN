---
title: RowMap 元素 (DataRecordSet_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f90dc76b-7f0b-dead-38c0-97062a7b76a6
description: 将数据记录集行映射到形状。
ms.openlocfilehash: 178ceb06d64bfc9ef50f75dd22f8bd94f09f5c33
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540768"
---
# <a name="rowmap-element-datarecordsettype-complextype-visio-xml"></a>RowMap 元素 (DataRecordSet_Type 复杂类型) (Visio XML)

将数据记录集行映射到形状。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[RowMap_Type](rowmap_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |记录集 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="RowMap" type="RowMap_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

****

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataRecordSet](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|PageID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |链接到由**RowID**标识的数据记录集行中的数据的形状的页面 ID。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|RowID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |行的行 ID, 在数据记录集中是唯一的。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|ShapeID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |链接到由**RowID**标识的数据记录集行中的数据的形状的形状 ID。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
   

