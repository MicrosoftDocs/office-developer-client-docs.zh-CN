---
title: RefreshConflict 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 373983f7-fc0c-95f6-7665-7ed47de82e5e
description: 指示数据记录集中的行链接到的形状在数据记录集刷新后发生冲突。
ms.openlocfilehash: 2da6f98cf7b047564331aaf5a4167e392927a155
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360135"
---
# <a name="refreshconflict-element-datarecordsettype-complextype-visio-xml"></a>RefreshConflict 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")

指示数据记录集中的行链接到的形状在数据记录集刷新后发生冲突。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[RefreshConflict_Type](refreshconflict_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |记录集 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="RefreshConflict" type="RefreshConflict_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataRecordSet](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|PageID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |冲突中涉及的形状的页面 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|RowID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |现在, 行的原始行 ID 在刷新数据后发生冲突。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|ShapeID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |冲突中涉及的形状的形状 ID。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
   

