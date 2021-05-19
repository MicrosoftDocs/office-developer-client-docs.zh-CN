---
title: 删除邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9ed166b4-6b7b-478f-bbe5-4115bb818ac0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 663eebfcd1b8862b22d8c822957024c4f31499de
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433162"
---
# <a name="deleting-a-message"></a>删除邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端可以在邮件打开时、用户阅读邮件时、关闭消息和用户查看内容表时删除该消息。 若要防止用户意外删除邮件，MAPI 将邮件删除定义为两个步骤：
  
1. 将邮件移动到已指定为"已删除邮件"文件夹的文件夹（其条目标识符存储在 PR_IPM_WASTEBASKET_ENTRYID ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md) **)** 属性中）来标记邮件进行删除。 
    
2. 通过调用 [IMAPIFolder：:D EleteMessages](imapifolder-deletemessages.md) 方法删除消息。 
    
当用户选择删除文件夹中除"已删除邮件"文件夹外的邮件时，请将其标记为删除。 只有在用户从"已删除邮件"文件夹中选择邮件时，才应从工作站中实际删除这些邮件。 您可以提示用户验证用户是否确实要执行删除操作。
  
 **删除邮件**
  
1. 与用户确认即将删除是有意的。
    
2. 确定要删除的文件夹的父文件夹。 如果是"已删除邮件"文件夹或"已删除邮件"文件夹中的子文件夹，请调用 [IMAPIFolder：:D eleteMessages](imapifolder-deletemessages.md) 删除邮件。 
    
3. 如果该文件夹未包含在"已删除邮件"文件夹中，请调用 [IMAPIFolder：：CopyMessages，](imapifolder-copymessages.md) 同时将 MESSAGE_MOVE 标志设置为将邮件重定位到"已删除邮件"文件夹。 
    

