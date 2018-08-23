---
title: PidLidTaskLastDelegate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskLastDelegate
api_type:
- COM
ms.assetid: 5eb8c1ce-063f-4273-acba-e6f9c994e7d3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f33443531e5affd358669225044b2d63c909aff1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575054"
---
# <a name="pidlidtasklastdelegate-canonical-property"></a>PidLidTaskLastDelegate 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 名称最近分配或已分配任务的用户。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskLastDelegate  <br/> |
|属性进行设置：  <br/> |PSETID_Task  <br/> |
|长 ID （盖）：  <br/> |0x00008125  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>注解

发送任务请求之前, 客户端将该属性设置为任务分配人的名称。 发送任务响应前, 客户端将该属性设置为任务受理人的名称。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义模型的任务、 任务分配和任务更新电子等效项的多个对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

