---
title: PidLidTaskAssigners 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskAssigners
api_type:
- COM
ms.assetid: 07500bd0-bcff-4b03-8ed3-80508875e253
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 97a4915d5422f6c5463ed399835172725b83407f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385072"
---
# <a name="pidlidtaskassigners-canonical-property"></a>PidLidTaskAssigners 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含条目，表示任务 assigners 的堆栈。 最新的任务分配人显示在堆栈的顶部。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskMyDelegators  <br/> |
|属性进行设置：  <br/> |PSETID_Task  <br/> |
|长 ID （盖）：  <br/> |0x00008117  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>说明

客户端接收任务请求时，它将追加到此属性，在[[MS OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)，值，该值代表任务的发件人的条目中定义的结构。 当客户端收到任务拒绝时，客户端从此属性中删除最后一个任务分配人条目。 当客户端发送的任务响应时，客户端会将其发送到最后一个任务分配人列入此属性的值。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义模型的任务、 任务分配和任务更新电子等效项的多个对象 
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

