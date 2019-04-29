---
title: 打开邮件文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e37fc9d8-433b-41b4-84f2-42a952063f35
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 305b0534f828ea72c1e116fd38fb8f578062e32e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407534"
---
# <a name="opening-message-text"></a>打开邮件文本

**适用于**：Outlook 2013 | Outlook 2016 
  
邮件的文本存储在其 " **pr\_正文**" 属性或 " **\_pr RTF\_" 压缩**属性中。 有关详细信息, 请**参阅\_pr 正文**([PidTagBody](pidtagbody-canonical-property.md)) **、\_pr HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 和**pr\_RTF\_压缩**([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))。 

如果你支持 rtf 格式 (rtf), 请打开 " **PR\_RTF_COMPRESSED**"。 如果您不支持 RTF, 请打开 **"\_PR 正文**"。 由于邮件的文本可能会很大而不管是否已对其进行格式设置, 因此请使用**IMAPIProp:: OpenProperty**打开这些属性。 有关详细信息, 请参阅[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)。
  
### <a name="to-display-formatted-message-text"></a>显示已设置格式的邮件文本
  
1. 如果您使用的是非 RTF 感知邮件存储, 则在 store 的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中缺少 STORE_RTF_OK 标志时表示:
    
    1. 调用邮件的**IMAPIProp:: GetProps**方法以检索**PR_RTF_IN_SYNC**属性。 有关详细信息, 请参阅[IMAPIProp:: GetProps](imapiprop-getprops.md) and **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))。
        
    2. 调用 RTFSync 以将邮件的 PR_BODY 属性与**PR_RTF_COMPRESSED**属性同步。 有关详细信息, 请参阅[RTFSync](rtfsync.md)、 **PR_BODY**和**PR_RTF_COMPRESSED**。 如果由于属性不存在或设置为 FALSE, 则对检索**PR_RTF_IN_SYNC**的调用失败时传递 RTF_SYNC_BODY_CHANGED 标志。 
        
    3. 如果**RTFSync**返回 TRUE (指示所做的更改), 则调用邮件的**IMAPIProp:: SaveChanges**方法以永久存储它们。 有关详细信息, 请参阅[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)。
    
2. 无论您是否使用的是 RTF 感知邮件存储区:
    
    1. 调用**IMAPIProp:: OpenProperty**以打开**PR_RTF_COMPRESSED**属性。 有关详细信息, 请参阅[IMAPIProp:: OpenProperty](imapiprop-openproperty.md) and **PR_RTF_COMPRESSED**。
        
    2. 如果**PR_RTF_COMPRESSED**不可用, 则调用**OpenProperty**以打开**PR_BODY**属性。 
        
    3. 调用**WrapCompressedRTFStream**函数以创建压缩的 RTF 数据的未压缩版本 (如果可用)。 有关详细信息, 请参阅[WrapCompressedRTFStream](wrapcompressedrtfstream.md)。
        
    4. 将格式文本从流中复制到邮件窗体中的适当位置。 
    
### <a name="to-display-plain-message-text"></a>显示纯文本消息文本
  
1. 调用邮件的**IMAPIProp:: GetProps**方法以检索**PR_BODY**属性。 有关详细信息, 请参阅[IMAPIProp:: GetProps](imapiprop-getprops.md)。
    
2. 如果**GetProps**返回属性值结构或 MAPI_E_NOT_ENOUGH_MEMORY 中的属性类型的 PT_ERROR, 请调用邮件的**IMAPIProp:: OpenProperty**方法。 将**PR_BODY**作为属性标记, 将 IID_IStream 作为接口标识符进行传递。 有关详细信息, 请参阅[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)。
    
3. 将流中的纯文本复制到邮件窗体中的适当位置。 
    

