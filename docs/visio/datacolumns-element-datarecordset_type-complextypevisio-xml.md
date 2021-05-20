---
title: 'DataColumns 元素 (DataRecordSet_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 34e25349-d0fa-b3a0-425b-778184e9f58f
description: 包含数据记录集内的所有 DataColumn 元素。
ms.openlocfilehash: e42354076c5e3e34c118145e7ec7fcdbd4977372
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541195"
---
# <a name="datacolumns-element-datarecordset_type-complextype-visio-xml"></a>DataColumns 元素 (DataRecordSet_Type COMPLEXType)  (Visio XML) 

包含数据记录集内的所有 **DataColumn** 元素。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[DataColumns_Type](datacolumns_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |recordsets.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="DataColumns" type="DataColumns_Type" minOccurs="1" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataRecordSet](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataColumn](datacolumn-element-datacolumns_type-complextypevisio-xml.md) <br/> |[DataColumn_Type](datacolumn_type-complextypevisio-xml.md) <br/> |定义数据列在 Visio 用户界面的"外部数据"窗口中的显示方式，并定义数据列的数据类型和格式。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|SortAsc  <br/> |xsd：boolean  <br/> |可选  <br/> |数据排序所基于的列。  <br/> |xsd：boolean 类型的值。  <br/> |
|SortColumn  <br/> |xsd：string  <br/> |可选  <br/> |按升序排序 **SortColumn** 列 (1) 0 (0) 排序。  <br/> |xsd：string 类型的值。  <br/> |
   

