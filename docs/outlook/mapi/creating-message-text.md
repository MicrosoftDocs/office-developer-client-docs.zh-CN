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
  
虽然某些邮件是由收件人列表和主题行组成, 但大多数邮件的内容 (尤其是 IPM) 除外。注释邮件包括文本。 邮件文本可以是纯文本或格式的, 并存储在以下三个属性中: **PR\_BODY** ([PidTagBody](pidtagbody-canonical-property.md))、 **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))。 

如果您的客户端是纯文本, 请**设置\_PR 正文**。 如果您支持 rtf 格式的格式化文本, 请仅设置 " **PR_RTF_COMPRESSED** " 或 " **PR_RTF_COMPRESSED** " 和 " **PR\_正文**", 具体取决于所使用的邮件存储提供程序。 当 rtf 感知客户端使用的是 rtf 感知邮件存储时, 它只会设置**PR_RTF_COMPRESSED** 。 当 RTF 感知客户端使用非 RTF 感知邮件存储区时, 它会同时设置这两个属性。 如果您的客户端支持 HTML, 请设置**PR_HTML**属性。 
  
## <a name="determine-whether-your-message-store-supports-rich-text-format"></a>确定您的邮件存储区是否支持 rtf 格式
  
1. 调用邮件存储区的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。
    
2. 检查 STORE_RTF_OK 位。 如果设置了 STORE_RTF_OK, 则邮件存储提供程序支持 RTF 文本。 如果未设置, 则邮件存储提供程序仅支持纯文本。
    
## <a name="determine-whether-your-message-store-supports-html"></a>确定您的邮件存储区是否支持 HTML
  
1. 调用邮件存储区的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索**PR_STORE_SUPPORT_MASK**属性。 
    
2. 检查 STORE_HTML_OK 位。 如果设置了 STORE_HTML_OK, 则邮件存储提供程序支持 HTML 文本。 
    
## <a name="set-prrtfcompressed"></a>设置 PR\_RTF_COMPRESSED
  
1. 调用邮件的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法以打开**PR_RTF_COMPRESSED**属性, 指定 IID_IStream 作为接口标识符并设置 MAPI_CREATE 标志。 
    
2. 如果在邮件存储区的**PR_STORE_SUPPORT_MASK**属性中设置了 STORE_UNCOMPRESSED_RTF 位, 请调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数, 并传递 STORE_UNCOMPRESSED_RTF 标志。 
    
3. 通过调用其 * * IUnknown:: Release * * 方法释放原始流。 
    
4. 调用 * * IStream:: Write * * 或**IStream:: CopyTo**将消息文本写入从**WrapCompressedRTFStream**返回的流。
    
5. 调用**OpenProperty**方法返回的 stream 上的**Commit**和**Release**方法。 
    
在这种情况下, 如果邮件存储区提供程序支持 RTF, 则您已完成所有必需的操作。 您可以依赖邮件存储提供程序来处理邮件内容和格式的同步, 并在必要时创建 " **PR\_正文**" 属性。 RTF 感知邮件存储区调用[RTFSync](rtfsync.md)以处理同步。 如果 RTF\_SYNC_BODY_CHANGED 标志设置为 TRUE, 则提供程序将重新计算**PR_BODY**属性。 
  
如果您的邮件存储区提供程序不支持 rtf, 还必须通过设置**PR_BODY**属性来添加非 RTF 邮件内容。 
  
## <a name="set-prhtml"></a>设置 PR_HTML
  
1. 调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法以使用**IStream**接口打开**PR_HTML**属性。 
    
2. 调用**IStream:: write** , 用于将消息文本数据写入从**OpenProperty**返回的流。 
    
3. 调用**IStream:: commit**和**IUnknown:: Release** on stream 以提交更改并释放其内存。 
    
## <a name="set-prbody"></a>设置 PR_BODY
  
1. 调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法以使用**IStream**接口打开**PR_BODY**属性。 
    
2. 调用**IStream:: write** , 用于将消息文本数据写入从**OpenProperty**返回的流。 
    
3. 调用[RTFSync](rtfsync.md)函数以将文本与格式设置同步。 由于这是一封新邮件, 因此应设置 RTF_SYNC_RTF_CHANGED 和 RTF_SYNC_BODY_CHANGED 标志, 以指示邮件文本的 RTF 和纯文本版本已更改。 **RTFSync**将设置邮件存储提供程序所需的多个相关属性, 如**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)), 并将其写入邮件。
    
4. 调用**IStream:: commit**和**IUnknown:: Release** on stream 以提交更改并释放其内存。 
    

