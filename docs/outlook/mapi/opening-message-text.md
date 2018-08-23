---
title: 打开消息文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e37fc9d8-433b-41b4-84f2-42a952063f35
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7a2dbe8d2143fd330ae1f5ca5804e30b79909576
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569402"
---
# <a name="opening-message-text"></a>打开消息文本

**适用于**： Outlook 2013 |Outlook 2016 
  
存储的消息的文本中其**PR\_正文**属性或**PR\_RTF\_压缩**属性。 有关详细信息，请参阅**PR\_正文**([PidTagBody](pidtagbody-canonical-property.md))， **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 和**PR\_RTF\_压缩**([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))。 

如果您支持富文本格式 (RTF)，打开**PR\_RTF_COMPRESSED**。 如果您不支持 RTF，打开**PR\_正文**。 由于消息的文本可能很大无论设置格式，使用**IMAPIProp::OpenProperty**打开这些属性。 有关详细信息，请参阅[IMAPIProp::OpenProperty](imapiprop-openproperty.md)。
  
### <a name="to-display-formatted-message-text"></a>显示带格式的消息文本
  
1. 如果您使用的非 RTF 注意消息存储，如缺少 STORE_RTF_OK 标志的存储**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中所示：
    
    1. 调用消息的**IMAPIProp::GetProps**方法来检索**PR_RTF_IN_SYNC**属性。 有关详细信息，请参阅[IMAPIProp::GetProps](imapiprop-getprops.md)和**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))。
        
    2. 调用 RTFSync **PR_RTF_COMPRESSED**属性与同步消息的 PR_BODY 属性。 有关详细信息，请参阅[RTFSync](rtfsync.md)、 **PR_BODY**和**PR_RTF_COMPRESSED**。 传递 RTF_SYNC_BODY_CHANGED 标记如果调用来检索**PR_RTF_IN_SYNC**失败，因为属性不存在或其设置为 FALSE。 
        
    3. 如果**RTFSync**返回 TRUE — 指示所做更改 — 呼叫消息的**IMAPIProp::SaveChanges**方法永久存储。 有关详细信息，请参阅[IMAPIProp::SaveChanges](imapiprop-savechanges.md)。
    
2. 无论您使用 RTF 感知消息存储：
    
    1. 调用**IMAPIProp::OpenProperty**打开**PR_RTF_COMPRESSED**属性。 有关详细信息，请参阅[IMAPIProp::OpenProperty](imapiprop-openproperty.md)和**PR_RTF_COMPRESSED**。
        
    2. 如果**PR_RTF_COMPRESSED**不可用，请调用**OpenProperty**打开**PR_BODY**属性。 
        
    3. 如果可用，请调用**WrapCompressedRTFStream**函数创建的压缩文件的 RTF 数据，未压缩的版本。 有关详细信息，请参阅[WrapCompressedRTFStream](wrapcompressedrtfstream.md)。
        
    4. 将格式化的文本从流复制到邮件窗体中的适当位置。 
    
### <a name="to-display-plain-message-text"></a>显示普通消息文本
  
1. 调用消息的**IMAPIProp::GetProps**方法来检索**PR_BODY**属性。 有关详细信息，请参阅[IMAPIProp::GetProps](imapiprop-getprops.md)。
    
2. 如果**GetProps**返回属性值结构或 MAPI_E_NOT_ENOUGH_MEMORY 任一 PT_ERROR 用于属性类型，调用消息的**IMAPIProp::OpenProperty**方法。 作为属性标记和 IID_IStream 接口标识传递**PR_BODY** 。 有关详细信息，请参阅[IMAPIProp::OpenProperty](imapiprop-openproperty.md)。
    
3. 将纯文本从流复制到邮件窗体中的适当位置。 
    

