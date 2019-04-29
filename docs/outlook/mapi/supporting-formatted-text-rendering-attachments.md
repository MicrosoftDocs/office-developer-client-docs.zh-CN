---
title: 支持格式化的文本呈现附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 68abe85b-5dc0-40d0-8917-30ea002aa816
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5f03530f994fd13e7dc4c7eaa4124900c28e613b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405294"
---
# <a name="supporting-formatted-text-rendering-attachments"></a>支持格式化文本: 呈现附件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
一种客户端应用程序, 致力于在邮件的附件呈现过程中设置这些附件的**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性。 不介意呈现放置的客户端将此属性设置为 unset。
  
当客户端打开包含附件的邮件时, 它会尝试检索每个附件的**PR_RENDERING_POSITION**属性, 以确定应在邮件文本中呈现附件的位置。 客户端可以使用下列方法之一来检索**PR_RENDERING_POSITION**:
  
- [IMAPIProp:: GetProps](imapiprop-getprops.md)在打开的附件中检索**PR_RENDERING_POSITION**属性。 
    
- [IMessage:: GetAttachmentTable](imessage-getattachmenttable.md)在打开的邮件上检索其附件表。 **PR_RENDERING_POSITION**是所有附件表中的必需列。 这是首选方法, 因为它将导致更好的性能。 
    
RTF 感知邮件存储区可以选择是返回**PR_RENDERING_POSITION**的准确值还是近似值。 由于在要求提供邮件的**PR_BODY**属性时, 邮件存储会重新计算附件的**PR_RENDERING_POSITION**值, 因此某些 RTF 感知邮件存储只有当客户端要求首次使用时, 才能保证呈现位置的准确性。**PR_BODY**。 允许 RTF 感知邮件存储提供具有近似呈现位置值的客户端, 以提高性能。 提供近似而不是精确的呈现位置可节省时间, 并且在大多数情况下已足够。 
  
RTF 感知邮件存储应根据负责创建该附件的客户端指定的值来使其近似。 尽管所有客户端都应设置**PR_RENDERING_POSITION**, 但应准备好邮件存储提供程序, 以处理缺少的情况。 当客户端未设置**PR_RENDERING_POSITION**时, 邮件存储可以将其设置为-1, 以指示呈现位置不在邮件文本中。 呈现位置为-1 的附件可以显示在邮件中的任何位置, 具体取决于客户端。 许多客户端将这些类型的附件放在邮件的顶部。
  
**PR_RENDERING_POSITION**属性的精确度取决于邮件存储是否保存邮件的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性或仅**PR_RTF_COMPRESSED**。 如果客户端生成**PR_BODY** , 并且邮件存储区将与格式化的文本一起保存, 则呈现位置将准确。 但是, 如果邮件存储区必须生成其自己的**PR_BODY**版本, 因为它仅保存**PR_RTF_COMPRESSED**, 所以呈现位置可能会变得有些不准确。 这是因为客户端和邮件存储提供程序生成**PR_BODY**属性的方式不同。 
  
若要计算准确的**PR_RENDERING_POSITION**值, 则 RTF 存储将使用嵌入的格式化文本中的标记。 可以调用实用工具函数**RTFSync**来执行此计算并更新附件的呈现位置。 根据可用的状态信息量, 邮件存储可以将 RTF_SYNC_BODY_CHANGED、RTF_SYNC_RTF_CHANGED 或这两个值传递给[RTFSync](rtfsync.md)。
  

