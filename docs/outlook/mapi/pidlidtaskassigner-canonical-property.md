---
title: PidLidTaskAssigner 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskAssigner
api_type:
- COM
ms.assetid: f7047e4e-0fb3-476b-9568-8f1135e6d970
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ef5f78fa36632227311d037ee61085c677920fb1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400563"
---
# <a name="pidlidtaskassigner-canonical-property"></a>PidLidTaskAssigner 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 上次的用户分配任务名称。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskDelegator  <br/> |
|属性进行设置：  <br/> |PSETID_Task  <br/> |
|长 ID （盖）：  <br/> |0x00008121  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>说明

如果尚未分配任务，不设置此属性。 任务工作负责人收到任务要求后，客户端将该属性进行设置，因为属性将不是设置任务的任务分配人的副本。 当客户端中添加或删除任务分配人的任务分配人列表中的**dispidTaskMyDelegators** ([PidLidTaskAssigners](pidlidtaskassigners-canonical-property.md)) 属性， **dispidTaskDelegator** ([PidLidTaskAssigner](pidlidtaskassigner-canonical-property.md)) 属性必须设置为添加或已删除的任务分配人。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义模型的任务、 任务分配和任务更新电子等效项的多个对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

