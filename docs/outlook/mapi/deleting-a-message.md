---
title: 删除邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9ed166b4-6b7b-478f-bbe5-4115bb818ac0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ad891a9884e72aa352dc114232cd5951c590272f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585099"
---
# <a name="deleting-a-message"></a>删除邮件

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
当处于打开状态，并且用户阅读，或者关闭和用户正在查看的内容表时客户端可以删除一条消息。 若要防止用户无意删除一条消息，MAPI 时，可定义邮件删除为两个步骤：
  
1. 移到被指定为已删除邮件文件夹的文件夹将其标记为删除一条消息 — **PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) 属性中存储其项标识符的文件夹。 
    
2. 通过调用[IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md)方法删除邮件。 
    
当用户选择要删除一条消息已删除邮件文件夹之外的文件夹中时，将其标记为删除。 仅当用户选择从已删除邮件文件夹中的邮件时，才应邮件物理删除从工作站。 您可以提示用户确认用户真正用于执行删除操作。
  
 **若要删除一条消息**
  
1. 与用户确认即将删除是有意。
    
2. 确定要删除的文件夹的父级。 如果是已删除邮件文件夹还是已删除邮件文件夹中的子文件夹，调用[IMAPIFolder::DeleteMessages](imapifolder-deletemessages.md)要删除该消息。 
    
3. 如果文件夹不包含在已删除邮件文件夹中，调用[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)设置重定位到已删除邮件文件夹的邮件 MESSAGE_MOVE 标志。 
    

