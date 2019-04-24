---
title: PidLidTaskStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskStatus
api_type:
- COM
ms.assetid: 809776b7-ff00-4a52-84b9-8b5fb5f5c3e3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d058b42ad7d1a1b8387aa5b9a1a65ea160d90b02
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316665"
---
# <a name="pidlidtaskstatus-canonical-property"></a>PidLidTaskStatus 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定用户的任务进度状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskStatus  <br/> |
|属性集:  <br/> |PSETID_Task  <br/> |
|长 ID (盖子):  <br/> |0x00008101  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>注解

此属性的值必须设置为以下值之一。
  
|**Value**|**说明**|
|:-----|:-----|
|0x00000000  <br/> |用户尚未开始对任务执行操作。 如果设置了此值, 则**dispidPercentComplete** ([PidLidPercentComplete](pidlidpercentcomplete-canonical-property.md)) 必须为0.0。  <br/> |
|0x00000001  <br/> |用户在此任务上的工作正在进行中。 如果设置了此值, 则**dispidPercentComplete**必须大于0.0 且小于1.0。  <br/> |
|0x00000002  <br/> |此任务的用户工作已完成。 如果设置了此值, 则**dispidPercentComplete**必须为 1.0 **, dispidTaskDateCompleted** ([PidLidTaskDateCompleted](pidlidtaskdatecompleted-canonical-property.md)) 必须为当前日期, 并且**dispidTaskComplete** ([PidLidTaskComplete](pidlidtaskcomplete-canonical-property.md)) 必须为 TRUE。  <br/> |
|0x00000003  <br/> |用户正在等待其他人。  <br/> |
|0x00000004  <br/> |用户已延迟任务的工作。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义为任务、任务分配和任务更新的电子等效项建模的多个对象。
    
[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定与标记相关的属性和操作。
    
[[毫秒-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> 指定用于创建和定位邮箱中的特殊文件夹的属性和操作。
    
[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> 在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理客户端与服务器之间的数据传输的顺序和流。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[PidLidPercentComplete 规范属性](pidlidpercentcomplete-canonical-property.md)
  
[PidLidTaskDateCompleted 规范属性](pidlidtaskdatecompleted-canonical-property.md)
  
[PidLidTaskComplete 规范属性](pidlidtaskcomplete-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

