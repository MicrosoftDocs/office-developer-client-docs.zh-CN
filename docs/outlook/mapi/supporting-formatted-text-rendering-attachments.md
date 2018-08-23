---
title: 支持呈现附件的格式化的文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 68abe85b-5dc0-40d0-8917-30ea002aa816
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1b6339d768ac476c24ce988ba761270a50d47464
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580311"
---
# <a name="supporting-formatted-text-rendering-attachments"></a>支持格式化文本：显示附件

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
没及其附件的邮件中呈现其中一个客户端应用程序设置消息组合期间这些附件的**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性。 不关心呈现位置的客户端离开此属性未设置。
  
当客户端打开一封邮件的附件时，它会尝试检索每个附件**PR_RENDERING_POSITION**属性可以确定消息文本中应呈现附件的位置。 客户端可以使用下列方法之一来检索**PR_RENDERING_POSITION**:
  
- [IMAPIProp::GetProps](imapiprop-getprops.md)上打开的附件检索**PR_RENDERING_POSITION**属性。 
    
- 在打开的邮件，若要检索其附件表[IMessage::GetAttachmentTable](imessage-getattachmenttable.md) 。 **PR_RENDERING_POSITION**是所有附件表中所需的列。 这是首选的方法，因为它会导致更好的性能。 
    
RTF 感知消息存储可以选择是否要为**PR_RENDERING_POSITION**返回准确或近似的值。 因为邮件存储重新计算的附件**PR_RENDERING_POSITION**值当询问消息的**PR_BODY**属性时，某些 RTF 感知消息存储仅保证呈现位置的准确性时客户端要求首先**PR_BODY**。 RTF 感知消息存储被允许客户端提供近似呈现位置值，以提高性能。 提供一个大概而不准确呈现位置节省时间并对大多数情况下已足够。 
  
RTF 感知消息存储应底其近似上指定由客户端负责创建附件的值。 虽然所有客户端应设置**PR_RENDERING_POSITION**，消息存储提供程序应准备处理缺少的可能性。 当客户端不设置**PR_RENDERING_POSITION**时，消息存储可以将其设置为-1，以指示呈现位置不在消息文本。 可以在任何位置，具体取决于客户端在邮件内部显示具有为-1 呈现位置的附件。 客户端多位置这些类型的顶部的邮件的附件。
  
精确度**PR_RENDERING_POSITION**属性取决于是否的消息存储保存消息**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性或仅为**PR_RTF_COMPRESSED**。 如果客户端将生成**PR_BODY** ，并且消息存储保存以及格式化文本，将准确的呈现位置。 但是，如果消息存储库必须生成**PR_BODY**自己版本，因为它只保存**PR_RTF_COMPRESSED**，则可能将 ア ネ 较不准确的呈现位置。 这是由于在客户端和消息存储提供程序生成的**PR_BODY**属性的方式的差异。 
  
若要计算的准确**PR_RENDERING_POSITION**值，RTF 感知的存储，请使用带格式文本中嵌入的标记。 **RTFSync**的实用工具函数可调用它以执行此计算并更新附件的呈现位置。 根据可用的状态信息量，消息存储库可以向[RTFSync](rtfsync.md)传递 RTF_SYNC_BODY_CHANGED、 RTF_SYNC_RTF_CHANGED 或二者的值。
  

