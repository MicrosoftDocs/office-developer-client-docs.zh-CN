---
title: DataConnection 元素 （DataConnections_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6aab8be3-b236-029b-1df3-b6860d4f4586
description: 使一个或多个 DataRecordset 元素和与非 XML 数据源之间的通信抽象化。
ms.openlocfilehash: 0073c329ec9149263530421531522c4d0b95633d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399422"
---
# <a name="dataconnection-element-dataconnectionstype-complextype-visio-xml"></a>DataConnection 元素 （DataConnections_Type 复杂类型） (Visio XML)

使一个或多个**DataRecordset**元素和与非 XML 数据源之间的通信抽象化。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[DataConnection_Type](dataconnection_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |connections.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="DataConnection" type="DataConnection_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[DataConnections](dataconnections-elementvisio-xml.md) <br/> |[DataConnections_Type](dataconnections_type-complextypevisio-xml.md) <br/> |包含文档的**DataConnection**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|AlwaysUseConnectionFile  <br/> |化  <br/> |可选  <br/> |默认值为 false。 有关详细信息，请参阅"说明"。  <br/> |化类型的值。  <br/> |
|命令  <br/> |xsd: string  <br/> |可选  <br/> |用于查询数据源的命令字符串。  <br/> |Xsd: string 类型的值。  <br/> |
|ConnectionString  <br/> |xsd: string  <br/> |可选  <br/> |用于定义连接到数据源所需的参数的连接字符串。  <br/> |Xsd: string 类型的值。  <br/> |
|FileName  <br/> |xsd: string  <br/> |必需  <br/> |连接文件的名称。 有关详细信息，请参阅"说明"。  <br/> |Xsd: string 类型的值。  <br/> |
|FriendlyName  <br/> |xsd: string  <br/> |可选  <br/> |数据连接的用户提供的名称。  <br/> |Xsd: string 类型的值。  <br/> |
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |由 Visio 分配对于给定的连接，唯一的文档中的 ID。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|Timeout  <br/> |xsd:unsignedInt  <br/> |可选  <br/> |以分钟为单位试图建立在终止尝试之前等待时间。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
   

