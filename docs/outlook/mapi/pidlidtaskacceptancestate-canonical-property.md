---
title: PidLidTaskAcceptanceState 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskAcceptanceState
api_type:
- COM
ms.assetid: 7012f524-bc66-48ea-85b5-163e05029d35
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b42be4b42d085aba8999a8c3f1a780ed972fa136
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331288"
---
# <a name="pidlidtaskacceptancestate-canonical-property"></a>PidLidTaskAcceptanceState 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示任务的接受状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskDelegValue  <br/> |
|属性集:  <br/> |PSETID_Task  <br/> |
|长 ID (盖子):  <br/> |0x0000812A  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>注解

下表显示了此属性的可能值。
  
|**Value**|**说明**|
|:-----|:-----|
|0x00000000  <br/> |未分配任务。  <br/> |
|0x00000001  <br/> |任务的接受状态为 "未知"。  <br/> |
|0x00000002  <br/> |任务受理人接受了任务。 此值是在客户端处理任务接受时设置的。  <br/> |
|0x00000003  <br/> |任务受理人拒绝了任务。 此值在客户端处理任务拒绝时设置。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义为任务、任务分配和任务更新的电子等效项建模的多个对象。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

