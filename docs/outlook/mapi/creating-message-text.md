---
title: 创建邮件文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 70d1fb24-91a9-4043-8c9d-be1523012e6b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5b4a4107d6326a61f50a4023ebc2538f699224b5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428002"
---
# <a name="creating-message-text"></a>创建邮件文本

**适用于**：Outlook 2013 | Outlook 2016 
  
尽管某些邮件只由收件人列表和主题行决定，但大多数邮件的内容，尤其是 IPM。Note messages， includes text. 邮件文本可以是纯文本或格式文本，并存储在三个属性中 **：PR \_ BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 、PR **\_ HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 和 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 。 

如果你的客户端是基于纯文本的，请设置 **PR \_ BODY**。 如果支持 RTF 格式格式 (RTF) 格式的文本，请仅设置 **PR_RTF_COMPRESSED** 或同时设置 PR_RTF_COMPRESSED 和 PR **\_ BODY，** 具体取决于您使用的邮件存储提供程序。  当 RTF 感知客户端使用 RTF 感知邮件存储时，它将仅 **PR_RTF_COMPRESSED邮件。** 当 RTF 感知客户端使用非 RTF 感知邮件存储时，它将设置这两个属性。 如果客户端支持 HTML，请设置 **PR_HTML** 属性。 
  
## <a name="determine-whether-your-message-store-supports-rich-text-format"></a>确定邮件存储是否支持格式文本格式
  
1. 调用消息存储的[IMAPIProp：：GetProps](imapiprop-getprops.md)方法来检索 PR_STORE_SUPPORT_MASK  ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。
    
2. 检查STORE_RTF_OK位。 如果STORE_RTF_OK，则邮件存储提供程序支持 RTF 文本。 如果未设置，则邮件存储提供程序仅支持纯文本。
    
## <a name="determine-whether-your-message-store-supports-html"></a>确定邮件存储是否支持 HTML
  
1. 调用消息存储的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索 **PR_STORE_SUPPORT_MASK** 属性。 
    
2. 检查STORE_HTML_OK位。 如果STORE_HTML_OK，则邮件存储提供程序支持 HTML 文本。 
    
## <a name="set-pr_rtf_compressed"></a>设置 PR \_ RTF_COMPRESSED
  
1. 调用消息的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法以打开 **PR_RTF_COMPRESSED** 属性，将 IID_IStream 指定为接口标识符并设置 MAPI_CREATE 标志。 
    
2. 调用 [WrapCompressedRTFStream](wrapcompressedrtfstream.md) 函数，如果在邮件存储的 PR_STORE_SUPPORT_MASK 属性中设置了 STORE_UNCOMPRESSED_RTF 位，则传递 **STORE_UNCOMPRESSED_RTF** 标志。 
    
3. 通过调用其 ** IUnknown：：Release ** 方法释放原始流。 
    
4. 调用 ** IStream：：Write ** 或 **IStream：：CopyTo** 将消息文本写入 **从 WrapCompressedRTFStream 返回的流**。
    
5. 对从 **OpenProperty** 方法返回的流调用 Commit 和 **Release** 方法。  
    
此时，如果邮件存储提供程序支持 RTF，则已完成所有必需操作。 您可以依赖邮件存储提供程序来处理邮件内容和格式的同步，并在必要时创建 **PR \_ BODY** 属性。 RTF 感知邮件存储调用 [RTFSync](rtfsync.md) 来处理同步。 如果 RTF SYNC_BODY_CHANGED设置为 TRUE，提供程序将重新 \_ 编译PR_BODY属性。  
  
如果邮件存储提供程序不支持 RTF，则还必须通过设置 PR_BODY 添加 **非 RTF** 邮件内容。 
  
## <a name="set-pr_html"></a>设置PR_HTML
  
1. 调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法以使用 **IStream** **PR_HTML** 打开属性。 
    
2. 调用 **IStream：：Write** 以将邮件文本数据写入从 **OpenProperty 返回的流**。 
    
3. 在 **流上调用 IStream：：Commit** 和 **IUnknown：：Release** 以提交更改并释放其内存。 
    
## <a name="set-pr_body"></a>设置PR_BODY
  
1. 调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法以使用 **IStream** **PR_BODY打开** PR_BODY 属性。 
    
2. 调用 **IStream：：Write** 以将邮件文本数据写入从 **OpenProperty 返回的流**。 
    
3. 调用 [RTFSync](rtfsync.md) 函数以将文本与格式同步。 因为这是新邮件，请同时设置 RTF_SYNC_RTF_CHANGED 和 RTF_SYNC_BODY_CHANGED 标志，以指示 RTF 和纯文本版本的邮件文本已更改。 **RTFSync** 将设置邮件存储提供程序所需的几个相关属性，如 **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) ，并写入邮件。
    
4. 在 **流上调用 IStream：：Commit** 和 **IUnknown：：Release** 以提交更改并释放其内存。 
    

