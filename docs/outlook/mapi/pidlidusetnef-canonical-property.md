---
title: PidLidUseTnef 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidUseTnef
api_type:
- COM
ms.assetid: 954048d6-e2eb-43e7-b52c-c2f047bb84a4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 56f6e2355ee2e64cc766bafe27cd59454e210ab6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384977"
---
# <a name="pidlidusetnef-canonical-property"></a>PidLidUseTnef 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定该邮件从 MAPI 转换为多用途 Internet 邮件扩展 (MIME) 或简单邮件传输协议 (SMTP) 格式时，是否应在上一条消息中包括传输中性封装格式 (TNEF)。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidUseTNEF  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x00008582  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |运行时配置  <br/> |
   
## <a name="remarks"></a>说明

此属性指定该邮件从 TNEF 转换为 MIME 或 SMTP 格式时是否应在 TNEF 包括上一条消息。 此属性可能不存在，并且如果是这样，TNEF 不能包含对邮件。
  
此属性仅适用时邮件发送的 POP3/SMTP 邮件帐户并不适用于由其他提供程序，例如 Microsoft Exchange Server 发送邮件时。
  
在某些情况下，如时投票按钮处于启用状态或嵌入的 OLE 对象附加到邮件中，Outlook 可以设置此属性以强制使用 TNEF。
  
**PR_MSG_EDITOR_FORMAT** ([PidTagMessageEditorFormat](pidtagmessageeditorformat-canonical-property.md)) 属性可用于强制实施仅纯文本，而不是 TNEF，发送邮件时。 **PidLidUseTNEF**重写**PR_MSG_EDITOR_FORMAT**中的设置，因此想要强制对传出邮件的纯文本应用程序应还寻找**PidLidUseTNEF** ，并将其重置为 FALSE。 此外外, 接程序必须删除所需 TNEF 以避免在最后发送的消息上不可用的附件的邮件功能。 
  
使用**CCSF_USE_TNEF**标志调用[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)将传出的 MAPI 邮件转换为 MIME 流时还可以强制实施 TNEF。 这适用即使**PidLidUseTNEF**未设置。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
[[MS OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 进行编码和解码为有效的流表示形式的消息和附件对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

