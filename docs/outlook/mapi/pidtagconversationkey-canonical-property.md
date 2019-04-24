---
title: PidTagConversationKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 52c97d6c-7f4b-4522-aeac-0c1ed8475952
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 00c65dae9bc29fe9cdb310b819ba99d6d46ebfe3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334697"
---
# <a name="pidtagconversationkey-canonical-property"></a>PidTagConversationKey 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含仅在查找 IPM 时在 Microsoft Outlook 中使用的对话密钥 **。MessageManager**邮件, 如包含邮局协议 (POP3) 帐户的下载历史记录的邮件。 在 Microsoft Exchange Server 中, 此属性已被弃用。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONVERSATION_KEY  <br/> |
|标识符:  <br/> |0x000B  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |常规邮件  <br/> |
   
## <a name="remarks"></a>注解

将电子邮件作为对话访问并将邮件属性转换为[非特定于传输的封装格式 (TNEF)](transport-neutral-encapsulation-format-tnef.md)时, 不要使用此属性;相反, 请使用[PidTagConversationIndex](pidtagconversationindex-canonical-property.md)和[PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)规范属性。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Microsoft Exchange Server 协议规范的引用。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定在电子邮件对象上允许的属性和操作。
    
[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 将邮件和附件对象编码并解码为高效流表示形式。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IPM 子树](ipm-subtree.md)
  
[MAPI 特殊文件夹](mapi-special-folders.md)
  
[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

