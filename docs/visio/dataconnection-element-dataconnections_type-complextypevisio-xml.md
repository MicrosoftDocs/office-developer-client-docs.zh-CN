---
title: DataConnection 元素 (DataConnections_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6aab8be3-b236-029b-1df3-b6860d4f4586
description: 抽象化一个或多个 DataRecordset 元素与非 XML 数据源之间的通信。
ms.openlocfilehash: 619f3b4e3d9c93831cc23bc38fba3670107b2b51
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538401"
---
# <a name="dataconnection-element-dataconnectionstype-complextype-visio-xml"></a>DataConnection 元素 (DataConnections_Type 复杂类型) (Visio XML)

抽象化一个或多个**DataRecordset**元素与非 XML 数据源之间的通信。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[DataConnection_Type](dataconnection_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |连接 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="DataConnection" type="DataConnection_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataConnections](dataconnections-elementvisio-xml.md) <br/> |[DataConnections_Type](dataconnections_type-complextypevisio-xml.md) <br/> |包含文档的**DataConnection**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|AlwaysUseConnectionFile  <br/> |xsd: boolean  <br/> |可选  <br/> |默认值为 false。 有关详细信息，请参阅"说明"。  <br/> |Xsd: boolean 类型的值。  <br/> |
|Command  <br/> |xsd: string  <br/> |可选  <br/> |用于查询数据源的命令字符串。  <br/> |Xsd: string 类型的值。  <br/> |
|ConnectionString  <br/> |xsd: string  <br/> |可选  <br/> |定义连接到数据源所需参数的连接字符串。  <br/> |Xsd: string 类型的值。  <br/> |
|FileName  <br/> |xsd: string  <br/> |必需  <br/> |连接文件的名称。 有关详细信息，请参阅"说明"。  <br/> |Xsd: string 类型的值。  <br/> |
|FriendlyName  <br/> |xsd: string  <br/> |可选  <br/> |用户为数据连接提供的名称。  <br/> |Xsd: string 类型的值。  <br/> |
|ID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |由 Visio 为指定的连接分配的 ID, 在文档中是唯一的。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
|Timeout  <br/> |xsd: unsignedInt  <br/> |可选  <br/> |尝试在终止尝试之前建立连接时的等待时间 (以分钟为单位)。  <br/> |Xsd: unsignedInt 类型的值。  <br/> |
   

