---
title: 创建消息文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 70d1fb24-91a9-4043-8c9d-be1523012e6b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 38be3bc2df8931ca45da12e43436377545e8a977
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774757"
---
# <a name="creating-message-text"></a>创建消息文本

**适用于**： Outlook 
  
尽管某些消息组成的 nothing 比收件人列表和主题行，大多数消息，专门 IPM 的内容。注意邮件，包含文本。 消息文本可为纯文本或格式，并存储在三个属性： **PR\_正文**([PidTagBody](pidtagbody-canonical-property.md))， **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))。 

如果您的客户端，基于纯文本设置**PR\_正文**。 如果您支持格式化的文本富文本格式 (RTF) 中，设置仅**PR_RTF_COMPRESSED**或两个**PR_RTF_COMPRESSED**和**PR\_正文**，这取决于您使用的消息存储提供程序。 时的 RTF 感知客户端使用的为 RTF 感知的邮件存储区，仅设置**PR_RTF_COMPRESSED** 。 RTF 感知客户端使用的非 RTF 注意消息存储，将这两个属性。 如果您的客户端支持 HTML，设置**PR_HTML**属性。 
  
## <a name="determine-whether-your-message-store-supports-rich-text-format"></a>确定您的消息存储是否支持富文本格式
  
1. 调用的消息存储[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。
    
2. 检查 STORE_RTF_OK 位。 如果设置 STORE_RTF_OK，消息存储提供程序支持 RTF 的文本。 如果它未设置，消息存储提供程序支持纯文本。
    
## <a name="determine-whether-your-message-store-supports-html"></a>确定是否保存邮件支持 HTML
  
1. 调用的消息存储[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索**PR_STORE_SUPPORT_MASK**属性。 
    
2. 检查 STORE_HTML_OK 位。 如果设置 STORE_HTML_OK，消息存储提供程序支持的 HTML 文本。 
    
## <a name="set-prrtfcompressed"></a>设置 PR\_RTF_COMPRESSED
  
1. 调用消息的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法以打开**PR_RTF_COMPRESSED**属性，指定 IID_IStream 接口标识，并设置 MAPI_CREATE 标志。 
    
2. 调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数，如果 STORE_UNCOMPRESSED_RTF 位设置中的消息存储**PR_STORE_SUPPORT_MASK**属性传递 STORE_UNCOMPRESSED_RTF 标志。 
    
3. 通过调用释放原始流其 * * IUnknown::Release * * 方法。 
    
4. 调用 * * IStream::Write * * 或从**WrapCompressedRTFStream**返回**IStream::CopyTo** stream 中写入消息文本。
    
5. 对从**OpenProperty**方法返回的流调用的**提交**和**发布**方法。 
    
此时，消息存储提供程序支持 RTF，如果您已完成所有必需的。 您可以取决于消息存储提供程序来处理同步消息内容和格式设置并创建**PR\_正文**必要的属性。 RTF 感知消息存储调用[RTFSync](rtfsync.md)处理同步。 如果在 RTF\_SYNC_BODY_CHANGED 标志设置为 TRUE，则提供程序将重新计算**PR_BODY**属性。 
  
如果您的消息存储提供程序不支持 RTF，您还必须通过设置**PR_BODY**属性添加非 RTF 邮件内容。 
  
## <a name="set-prhtml"></a>设置 PR_HTML
  
1. 调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法使用**IStream**接口打开**PR_HTML**属性。 
    
2. 调用**IStream::Write**消息文本数据写入**OpenProperty**从返回的流。 
    
3. 对要提交的更改并释放其内存流调用**IStream::Commit**和**IUnknown::Release** 。 
    
## <a name="set-prbody"></a>设置 PR_BODY
  
1. 调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法使用**IStream**接口打开**PR_BODY**属性。 
    
2. 调用**IStream::Write**消息文本数据写入**OpenProperty**从返回的流。 
    
3. 调用[RTFSync](rtfsync.md)函数以同步带格式的文本。 由于这是一个新的邮件，设置的 RTF_SYNC_RTF_CHANGED 和 RTF_SYNC_BODY_CHANGED 标志指示已更改消息文本的 RTF 和纯文本版本。 **RTFSync**将设置多个相关的属性所需的消息存储提供程序，如**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))，并将它们写到邮件。
    
4. 对要提交的更改并释放其内存流调用**IStream::Commit**和**IUnknown::Release** 。 
    

