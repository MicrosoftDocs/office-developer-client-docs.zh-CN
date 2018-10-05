---
title: PidTagRoamingDatatypes 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRoamingDatatypes
api_type:
- COM
ms.assetid: a3336b61-01b6-47a7-9498-0a03878e91cb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fe5528f7605412d0cfd4b4b914e9b221c715e1b1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384260"
---
# <a name="pidtagroamingdatatypes-canonical-property"></a>PidTagRoamingDatatypes 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个位掩码，指示属性存在邮件的流。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ROAMING_DATATYPES  <br/> |
|标识符：  <br/> |0x7C06  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Configuration  <br/> |
   
## <a name="remarks"></a>说明

此属性必须设置为一个或多个下列值：
  
|**值**|**说明**|
|:-----|:-----|
|0x00000002  <br/> |指示文件夹关联的信息 （从故障） 邮件应包含词典流，序列化为固定的 XML 架构，并存储在**PR_ROAMING_DICTIONARY** ([PidTagRoamingDictionary](pidtagroamingdictionary-canonical-property.md)) 属性。 如果从故障消息不包含词典流，应用程序必须视为字典无任何条目。  <br/> |
|0x00000004  <br/> |指示从故障消息必须包含存储在**PR_ROAMING_XMLSTREAM** ([PidTagRoamingXmlStream](pidtagroamingxmlstream-canonical-property.md)) 属性使用任意 XML 架构的 XML 流。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)
  
> 指定的位置和客户端和服务器配置数据，如共享的类别列表和工作时间的属性。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

