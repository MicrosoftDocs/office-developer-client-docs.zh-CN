---
title: RefreshConflict 元素 （DataRecordSet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 373983f7-fc0c-95f6-7665-7ed47de82e5e
description: 指示链接到形状的数据记录集刷新后存在冲突的数据记录集中的行。
ms.openlocfilehash: 2da6f98cf7b047564331aaf5a4167e392927a155
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397399"
---
# <a name="refreshconflict-element-datarecordsettype-complextype-visio-xml"></a>RefreshConflict 元素 （DataRecordSet_Type 复杂类型） (Visio XML)

指示链接到形状的数据记录集刷新后存在冲突的数据记录集中的行。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[RefreshConflict_Type](refreshconflict_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |recordsets.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="RefreshConflict" type="RefreshConflict_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[数据记录集](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|PageID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |页面冲突中涉及的形状的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|RowID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |现在中后，刷新数据的冲突的行的原始的行 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ShapeID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |冲突中涉及的形状的形状 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
   

