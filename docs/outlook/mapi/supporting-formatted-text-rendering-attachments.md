---
title: 支持格式化文本呈现附件
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
# <a name="supporting-formatted-text-rendering-attachments"></a>支持格式化文本：呈现附件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
关注邮件附件呈现位置的客户端应用程序在邮件撰写期间为这些附件设置 **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性。 不需要呈现放置的客户端会取消设置此属性。
  
当客户端打开带有附件的邮件时，它会尝试检索每个附件的 **PR_RENDERING_POSITION** 属性，以确定附件应在邮件文本中的哪个位置呈现。 客户端可以使用下列方法之一来 **检索PR_RENDERING_POSITION：**
  
- [打开的附件上的 IMAPIProp：：GetProps](imapiprop-getprops.md)检索 PR_RENDERING_POSITION **属性。** 
    
- [打开的邮件上的 IMessage：：GetAttachmentTable](imessage-getattachmenttable.md) 检索其附件表。 **PR_RENDERING_POSITION** 是所有附件表中的必需列。 这是首选方法，因为它可提高性能。 
    
RTF 感知邮件存储可以选择是返回邮件的精确值还是近似 **PR_RENDERING_POSITION。** 由于当请求邮件 **的 PR_BODY** 属性时，邮件存储会重新计算附件的 **PR_RENDERING_POSITION** 值，因此某些 RTF 感知邮件存储仅保证客户端首先请求 PR_BODY 时呈现位置的准确性。  允许 RTF 感知邮件存储向客户端提供近似呈现位置值，以提高性能。 提供近似而不是准确的呈现位置可节省时间，并且足以满足大多数情况。 
  
RTF 感知邮件存储的近似值应基于负责创建附件的客户端指定的值。 尽管所有客户端都应 **PR_RENDERING_POSITION，** 但邮件存储提供程序应准备好处理其不存在的可能性。 当客户端未设置PR_RENDERING_POSITION时，邮件存储可以设置为 -1，以指示呈现位置不在消息文本中。 呈现位置为 -1 的附件可以显示在邮件内的任何位置，具体取决于客户端。 许多客户端将这些类型的附件放在邮件顶部。
  
PR_RENDERING_POSITION 属性的准确性 **取决于** 邮件存储是同时保存邮件的 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 和 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性还是仅保存 **PR_RTF_COMPRESSED**。 如果客户端 **生成PR_BODY且** 邮件存储会随格式化文本一起保存它，则呈现位置将准确。 但是，如果邮件存储 **必须** 生成其自己的 PR_BODY因为它仅保存 PR_RTF_COMPRESSED ，则呈现位置可能有些不准确。 这是因为客户端和邮件存储提供程序生成 PR_BODY **属性的方式** 不同。 
  
为了计算准确的 **PR_RENDERING_POSITION** 值，RTF 感知存储使用格式文本中嵌入的标记。 可以调用实用工具函数 **RTFSync** 来执行此计算并更新附件的呈现位置。 根据可用的状态信息量，邮件存储可以将两个值RTF_SYNC_BODY_CHANGED、RTF_SYNC_RTF_CHANGED或两个值传递到 [RTFSync](rtfsync.md)。
  

