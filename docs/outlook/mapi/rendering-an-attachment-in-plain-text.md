---
title: 以纯文本呈现附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 72b447e9-b4f2-4557-baf5-0afefe463749
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 587736e7ca2f30468b169a33cea34927f857382c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410873"
---
# <a name="rendering-an-attachment-in-plain-text"></a>以纯文本呈现附件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要在纯文本邮件中呈现附件，请检索附件的 **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性，并应用到 **PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 属性的数据。 有两种方法可以检索 **PR_RENDERING_POSITION：**
  
- 通过调用邮件 **的 IMessage：：OpenAttach** 方法打开附件，然后通过调用附件的 **IMAPIProp：：GetProps** 方法来请求 **PR_RENDERING_POSITION** 属性。 有关详细信息，请参阅 [IMessage：：OpenAttach](imessage-openattach.md) 和 [IMAPIProp：：GetProps](imapiprop-getprops.md)。
    
- 调用邮件的 **IMessage：：GetAttachmentTable** 方法以访问其附件表并检索包含 **PR_RENDERING_POSITION** 属性的列。 这种方法始终更可取。 有关详细信息，请参阅 [IMessage：：GetAttachmentTable](imessage-getattachmenttable.md)。
    
请记住，许多 RTF 感知邮件存储不会计算PR_RENDERING_POSITION直到客户端请求邮件的 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性。 在此之前 **，PR_RENDERING_POSITION通常** 表示一个近似值。 允许邮件存储提供程序向客户端提供近似值以提高性能。 
  
文件或二进制附件的呈现存储在其 **PR_ATTACH_RENDERING** 属性中。 可以选择使用与检索 PR_ATTACH_RENDERING相同的方法检索 **PR_RENDERING_POSITION：直接从** 附件或附件表中检索。 对于 **PR_ATTACH_RENDERING，** 第一个策略虽然比较耗时，但更安全。 由于某些邮件存储提供程序将表列截断为 255 字节，或在某些情况下为 510 字节，因此很难确定 **PR_ATTACH_RENDERING** 列包含完整呈现。 当直接从附件检索属性时，它将始终完整。 
  
OLE 和邮件附件均未 **PR_ATTACH_RENDERING。** 相反，OLE 1 附件的呈现信息存储在邮件文本流中。 对于 OLE 2 附件，它存储在存储对象的特殊子流中。 邮件附件的呈现信息通过表单管理器提供。 
  
 **检索邮件附件的呈现**
  
1. 使用邮件的邮件类访问表单管理器。
    
2. 访问表单管理器的 **PR_MINI_ICON** 属性。 有关详细信息，请参阅 **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 。
    

