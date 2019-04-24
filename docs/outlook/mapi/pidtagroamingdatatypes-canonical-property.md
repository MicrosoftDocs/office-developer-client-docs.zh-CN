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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359554"
---
# <a name="pidtagroamingdatatypes-canonical-property"></a>PidTagRoamingDatatypes 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含表示邮件中存在哪些流属性的位掩码。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ROAMING_DATATYPES  <br/> |
|标识符:  <br/> |0x7C06  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |配置  <br/> |
   
## <a name="remarks"></a>注解

此属性必须设置为以下一个或多个值:
  
|**Value**|**说明**|
|:-----|:-----|
|0x00000002  <br/> |指示文件夹关联的信息 (FAI) 邮件应包含字典流, 并序列化为固定 XML 架构并存储在**PR_ROAMING_DICTIONARY** ([PidTagRoamingDictionary](pidtagroamingdictionary-canonical-property.md)) 属性中。 如果 FAI 消息不包含字典流, 则应用程序必须将字典视为无条目。  <br/> |
|0x00000004  <br/> |指示 FAI 消息必须包含使用任意 XML 架构的**PR_ROAMING_XMLSTREAM** ([PidTagRoamingXmlStream](pidtagroamingxmlstream-canonical-property.md)) 属性中存储的 XML 流。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)
  
> 指定客户端和服务器配置数据的位置和属性, 如共享类别列表和工作时间。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

