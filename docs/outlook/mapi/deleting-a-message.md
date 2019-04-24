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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316833"
---
# <a name="deleting-a-message"></a>删除邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端可以在邮件处于打开状态且用户正在阅读, 或者关闭并查看内容表时, 删除该邮件。 为了防止用户无意中删除邮件, MAPI 将邮件删除定义为一个两步过程:
  
1. 通过将邮件移动到已被指定为 "已删除邮件" 文件夹的文件夹 (其条目标识符存储在**PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) 属性中), 可将邮件标记为待删除。 
    
2. 通过调用[IMAPIFolder::D eletemessages](imapifolder-deletemessages.md)方法删除邮件。 
    
当用户选择删除文件夹 ("已删除邮件" 文件夹除外) 中的邮件时, 请将其标记为删除。 仅当用户从 "已删除邮件" 文件夹中选择邮件时, 才应从工作站中实际删除邮件。 您可以提示用户确认用户确实打算执行删除。
  
 **删除邮件**
  
1. 向用户确认即将进行的删除是有意删除的。
    
2. 确定要删除的文件夹的父项。 如果是 "已删除邮件" 文件夹或 "已删除邮件" 文件夹中的子文件夹, 请调用[IMAPIFolder::D eletemessages](imapifolder-deletemessages.md)以删除邮件。 
    
3. 如果文件夹未包含在 "已删除邮件" 文件夹中, 则调用[IMAPIFolder:: CopyMessages](imapifolder-copymessages.md)并将邮件重定位到 "已删除邮件" 文件夹。 
    

