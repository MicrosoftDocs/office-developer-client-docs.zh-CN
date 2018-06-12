---
title: PidTagConversationKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 52c97d6c-7f4b-4522-aeac-0c1ed8475952
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 4aec52497e02e99423fa50f378cd35dbf366c37c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777502"
---
# <a name="pidtagconversationkey-canonical-property"></a>PidTagConversationKey 规范属性

  
  
**适用于**： Outlook 
  
包含查找**IPM 时仅在 Microsoft Outlook 中使用的会话密钥。MessageManager**邮件，例如包含邮局协议 (POP3) 帐户的下载历史记录的邮件。 Microsoft Exchange Server 中已弃用此属性。 
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_CONVERSATION_KEY  <br/> |
|标识符:  <br/> |0x000B  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

为对话并将其转换为[传输中性封装格式 (TNEF)](transport-neutral-encapsulation-format-tnef.md)邮件属性访问电子邮件时, 不使用此属性;而是使用[PidTagConversationIndex](pidtagconversationindex-canonical-property.md)和[PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)规范属性。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Microsoft Exchange Server 协议规范参考。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件消息对象在允许的操作。
    
[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 进行编码和解码为有效的流表示形式的消息和附件对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IPM 子树](ipm-subtree.md)
  
[MAPI 特殊文件夹](mapi-special-folders.md)
  
[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

