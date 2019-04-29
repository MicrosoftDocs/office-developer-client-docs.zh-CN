---
title: IPM 子树
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b5fc6084-722d-44e8-8637-f4160a4fb19b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 92c7a09d9d608ac31920d49b20f78bedd26f5fcd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421219"
---
# <a name="ipm-subtree"></a>IPM 子树

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 将在邮件存储区的根文件夹下创建一个文件夹树, 该树用于向人 (而不是计算机) 收件人发送邮件并从其接收邮件的所有客户端。 在人类收件人之间交换的邮件称为 "人际邮件", 此树称为 "人际邮件" 或 "IPM" 子树。 
  
传递存储区的 IPM 子树至少包含以下文件夹:
  
- Inbox
    
- 发件箱
    
- 已发送邮件
    
- 已删除邮件
    
以下是这些文件夹中每个文件夹的默认名称和角色;如果默认名称不合适, 客户端可以指定其自己的名称。 如果客户端在为邮件建立接收文件夹, 则 MAPI 会为这些文件夹分配默认名称和关联, 以防止无意中消失邮件。 
  
在 Microsoft Office Outlook 上下文中, IPM 子树由日历、联系人、任务、便笺和日记的其他默认文件夹组成。
  
"收件箱" 通常会保留传入的邮件, 而 "发件箱" 将保留传出邮件 (即等待发送的邮件)。 如果客户端将**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性设置为该文件夹的条目标识符, 则 "已发送邮件" 文件夹将保留每个已发送邮件的副本。 "已删除邮件" 文件夹包含标记为要删除的邮件。 
  
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

