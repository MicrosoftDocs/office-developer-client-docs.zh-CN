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
  
邮件的文本存储在其 **PR \_ BODY** 属性或 **PR \_ RTF \_ COMPRESSED 属性** 中。 有关详细信息，请参阅 **PR \_ BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 、PR **\_ HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 和 **PR \_ RTF \_ COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 。 

如果支持 RTF 格式格式 (RTF) ，请打开 **PR \_ RTF_COMPRESSED**。 如果不支持 RTF，请打开 **PR \_ BODY**。 由于无论邮件是否设置格式，邮件文本都可以很大，因此使用 **IMAPIProp：：OpenProperty** 打开这些属性。 有关详细信息，请参阅 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)。
  
### <a name="to-display-formatted-message-text"></a>显示带格式的邮件文本
  
1. 如果您使用的是非 RTF 感知邮件存储，如存储的 STORE_RTF_OK PR_STORE_SUPPORT_MASK ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 指示： 
    
    1. 调用邮件的 **IMAPIProp：：GetProps** 方法来检索 PR_RTF_IN_SYNC **属性。** 有关详细信息，请参阅 [IMAPIProp：：GetProps](imapiprop-getprops.md) 和 **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 。
        
    2. 调用 RTFSync 以将邮件的 PR_BODY 属性与 **PR_RTF_COMPRESSED** 属性同步。 有关详细信息，请参阅 [RTFSync、PR_BODY](rtfsync.md)和 **PR_RTF_COMPRESSED**。 如果RTF_SYNC_BODY_CHANGED检索的调用由于属性不存在或 **设置为** FALSE 而PR_RTF_IN_SYNC，请传递该标记。 
        
    3. 如果 **RTFSync** 返回 TRUE（指示进行了更改），请调用消息的 **IMAPIProp：：SaveChanges** 方法来永久存储它们。 有关详细信息，请参阅 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)。
    
2. 无论你是否使用 RTF 感知邮件存储：
    
    1. 调用 **IMAPIProp：：OpenProperty** 以打开 **PR_RTF_COMPRESSED** 属性。 有关详细信息，请参阅 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) and **PR_RTF_COMPRESSED**。
        
    2. 如果 **PR_RTF_COMPRESSED** 不可用，请调用 **OpenProperty** 以打开 **PR_BODY** 属性。 
        
    3. 调用 **WrapCompressedRTFStream** 函数以创建压缩 RTF 数据的未压缩版本（如果可用）。 有关详细信息，请参阅 [WrapCompressedRTFStream](wrapcompressedrtfstream.md)。
        
    4. 将格式化的文本从流复制到邮件窗体中的适当位置。 
    
### <a name="to-display-plain-message-text"></a>显示纯消息文本
  
1. 调用邮件的 **IMAPIProp：：GetProps** 方法来检索 PR_BODY **属性。** 有关详细信息，请参阅 [IMAPIProp：：GetProps](imapiprop-getprops.md)。
    
2. 如果 **GetProps** 返回PT_ERROR值结构中属性类型的值或MAPI_E_NOT_ENOUGH_MEMORY，请调用消息的 **IMAPIProp：：OpenProperty** 方法。 将 **PR_BODY** 作为属性标记传递，IID_IStream作为接口标识符传递。 有关详细信息，请参阅 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)。
    
3. 将纯文本从流复制到邮件窗体中的适当位置。 
    

