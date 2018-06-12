---
title: 支持带格式的传入邮件客户端职责中的文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 79727700-5ef1-4a29-9ed0-fd46c7de3202
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 863c95856f3198c74bb9d72881154676386f6a9f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778915"
---
# <a name="supporting-formatted-text-in-incoming-messages-client-responsibilities"></a>支持格式中传入消息的文本： 客户端职责

  
  
**适用于**： Outlook 
  
邮件系统之间传输邮件，如 MAPI 后台处理程序可确保的富文本格式保持同步的消息文本。 MAPI 后台处理程序调用[RTFSync](rtfsync.md)函数从中将其传递到传输提供程序的消息的换行版本。 传输提供程序保存到邮件通过调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法所做的更改，然后将其路由至新的收件人。 
  
当收件人的 RTF 感知客户端应用程序打开显示文本的消息时，它必须同步带格式文本，并打开**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 或**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))具体取决于该属性是否可用。
  
 **打开一条消息，RTF 感知客户端**
  
1. 调用**RTFSync**用的格式，如果消息存储不是 RTF 感知同步消息文本。 应在_ulFlags_参数中传递 RTF_SYNC_BODY_CHANGED 标志，如果**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性缺失或设置为 FALSE。 使用 RTF 感知消息存储的客户端不需要做**RTFSync**呼叫，因为它的负责消息存储库。 
    
2. 如果已更新的消息文本，请调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md) 。 
    
3. 调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)打开**PR_RTF_COMPRESSED**属性。 如果**PR_RTF_COMPRESSED**不可用，则应打开**PR_BODY**属性改为要显示的消息内容。 
    
4. 如果可用，请调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数创建的压缩文件的 RTF 数据，未压缩的版本。 
    
5. 向用户显示的未压缩的 RTF 数据或纯文本数据。
    
 **RTFSync**返回一个布尔值，指示已更新消息。 如果此值，则返回 TRUE，一些时间点进行更新永久调用**SaveChanges** 。 不必**RTFSync**返回后立即进行呼叫。 
  
> [!NOTE]
> 有许多组件处理的格式化的文本之前收到，因为没有损坏的可能性。 此损坏可能是来自消息存储提供程序、 的第三方应用程序、 网关或传输错误。 
  

