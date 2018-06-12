---
title: 呈现纯文本中的附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 72b447e9-b4f2-4557-baf5-0afefe463749
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 38db1d18f240188c7566a57afa23291a307446dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778627"
---
# <a name="rendering-an-attachment-in-plain-text"></a>呈现纯文本中的附件

  
  
**适用于**： Outlook 
  
若要呈现与纯文本邮件的附件，检索附件的**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性，并将其应用到**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 中的数据属性。 有两种方法来检索**PR_RENDERING_POSITION**:
  
- 通过调用消息的**IMessage::OpenAttach**方法打开附件，并通过调用附件的**IMAPIProp::GetProps**方法询问**PR_RENDERING_POSITION**属性。 有关详细信息，请参阅[IMessage::OpenAttach](imessage-openattach.md)和[IMAPIProp::GetProps](imapiprop-getprops.md)。
    
- 调用消息的**IMessage::GetAttachmentTable**方法访问其附件表并检索包含**PR_RENDERING_POSITION**属性的列。 这种方式始终是最好的。 有关详细信息，请参阅[IMessage::GetAttachmentTable](imessage-getattachmenttable.md)。
    
请记住，许多 RTF 感知的消息存储不计算**PR_RENDERING_POSITION**直到客户端请求一条消息的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性。 之前， **PR_RENDERING_POSITION**通常表示估计值。 消息存储提供程序允许客户端提供估计值以提高性能。 
  
文件或二进制附件呈现存储在其**PR_ATTACH_RENDERING**属性中。 您可以选择的相同方式检索**PR_ATTACH_RENDERING** ，如检索**PR_RENDERING_POSITION**： 直接从附件或附件表。 为**PR_ATTACH_RENDERING**，第一种策略，尽管更加耗时，更安全。 由于某些消息存储提供程序截断为 255 个字节，或在少数情况下 510 字节其表格列，因此很难以确保**PR_ATTACH_RENDERING**列中包含完整的呈现。 直接从附件中检索属性时，它始终将完成。 
  
OLE 和消息都不附件设置**PR_ATTACH_RENDERING**。 而是 OLE 1 附件的呈现信息存储在消息文本流。 对于 OLE 2 的附件，它存储在存储对象的特殊子流。 呈现邮件附件信息是可通过窗体管理器。 
  
 **若要检索的邮件附件的呈现**
  
1. 使用邮件的邮件类访问窗体管理器。
    
2. 访问表单经理**PR_MINI_ICON**属性。 有关详细信息，请参阅**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md))。
    

