---
title: 'DataConnections 元素 (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3cac0cd0-87ff-8c82-2d33-20070a505f4e
description: 包含文档的 DataConnection 元素。
ms.openlocfilehash: 5d45d1dcd76524c2144336235e8277cd51f8a138
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539180"
---
# <a name="dataconnections-element-visio-xml"></a>DataConnections 元素 (Visio XML) 

包含 **文档的 DataConnection** 元素。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[DataConnections_Type](dataconnections_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |connections.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="DataConnections" type="DataConnections_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

无。
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataConnection](dataconnection-element-dataconnections_type-complextypevisio-xml.md) <br/> |[DataConnection_Type](dataconnection_type-complextypevisio-xml.md) <br/> |抽象化一个或多个 **DataRecordset** 元素与非 XML 数据源之间的通信。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|NextID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |新连接的下一个可用 ID。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
   

