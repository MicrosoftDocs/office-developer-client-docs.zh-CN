---
title: PidTagSubmitFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubmitFlags
api_type:
- COM
ms.assetid: 9ea1c029-d53c-4c28-b413-560083b6215a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ca31aece48236227a03d8e2114f8af4b127b8f90
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384141"
---
# <a name="pidtagsubmitflags-canonical-property"></a>PidTagSubmitFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含指示的详细信息消息提交标志的位掩码。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SUBMIT_FLAGS  <br/> |
|标识符：  <br/> |0x0E14  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 非可传送  <br/> |
   
## <a name="remarks"></a>说明

可以为**PR_SUBMIT_FLAGS**位掩码设置一个或多个以下标志： 
  
SUBMITFLAG_LOCKED 
  
> MAPI 后台打印当前已锁定的消息。 
    
SUBMITFLAG_PREPROCESS 
  
> 需要预处理消息。 完 MAPI 后台处理程序预处理此消息时，它应调用[IMessage::SubmitMessage](imessage-submitmessage.md)方法。 消息存储提供程序可识别的后台处理程序，而不是客户端应用程序，呼叫**SubmitMessage**、 清除标志，并继续消息提交。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMsgStore::SetLockState](imsgstore-setlockstate.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

