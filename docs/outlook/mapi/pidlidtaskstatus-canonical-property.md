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
ms.openlocfilehash: a89cf096e3775b57035be60cab01e3d687770cf8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582572"
---
# <a name="pidlidtaskstatus-canonical-property"></a>PidLidTaskStatus 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定任务的用户的进度的状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskStatus  <br/> |
|属性进行设置：  <br/> |PSETID_Task  <br/> |
|长 ID （盖）：  <br/> |0x00008101  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>注解

此属性的值必须设置为下列选项之一。
  
|**值**|**说明**|
|:-----|:-----|
|0x00000000  <br/> |用户任务尚未开始工作。 如果设置此值，则**dispidPercentComplete** ([PidLidPercentComplete](pidlidpercentcomplete-canonical-property.md)) 必须是 0.0。  <br/> |
|0x00000001  <br/> |正在执行此任务的用户的工作。 如果设置此值，则**dispidPercentComplete**必须大于 0.0 且小于 1.0。  <br/> |
|0x00000002  <br/> |完成此任务的用户的工作。 如果设置此值， **dispidPercentComplete**必须是 1.0、 **dispidTaskDateCompleted** ([PidLidTaskDateCompleted](pidlidtaskdatecompleted-canonical-property.md)) 必须是当前日期，和**dispidTaskComplete** ([PidLidTaskComplete](pidlidtaskcomplete-canonical-property.md)) 必须为 TRUE。  <br/> |
|0x00000003  <br/> |用户正在等待其他人。  <br/> |
|0x00000004  <br/> |用户具有延迟任务的工时。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义模型的任务、 任务分配和任务更新电子等效项的多个对象。
    
[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定的属性和与标记的操作。
    
[[MS OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> 指定的属性和用于创建和邮箱中查找的特殊文件夹的操作。
    
[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为消息对象。
    
[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理顺序和客户端和服务器之间的数据传输的流。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[PidLidPercentComplete 规范属性](pidlidpercentcomplete-canonical-property.md)
  
[PidLidTaskDateCompleted 规范属性](pidlidtaskdatecompleted-canonical-property.md)
  
[PidLidTaskComplete 规范属性](pidlidtaskcomplete-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

