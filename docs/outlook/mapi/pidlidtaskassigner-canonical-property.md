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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340087"
---
# <a name="pidlidtaskassigner-canonical-property"></a>PidLidTaskAssigner 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 命名上次分配了该任务的用户。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskDelegator  <br/> |
|属性集：  <br/> |PSETID_Task  <br/> |
|LONG ID (的一) ：  <br/> |0x00008121  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>备注

如果尚未分配该任务，则此属性将取消设置。 由于客户端在任务接受者收到任务请求后设置此属性，因此不会在任务分配者的任务副本上设置该属性。 当客户端在 **dispidTaskMyDelegators** ([PidLidTaskAssigners](pidlidtaskassigners-canonical-property.md)) 属性中的任务分配者列表中添加或删除任务分配者时 **，dispidTaskDelegator** ([PidLidTaskAssigner](pidlidtaskassigner-canonical-property.md)) 属性必须设置为已添加或删除的任务分配者。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

