---
title: MAPI 查看文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1936ec2-bf8a-4242-a41d-64d26b813bd0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cb26771e9968175ab67366e35cf019ce23d51b8d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776352"
---
# <a name="mapi-view-folders"></a>MAPI 查看文件夹

  
  
**适用于**： Outlook 
  
查看文件夹是根文件夹，包含定义替代显示布局人际邮件 (IPM) 文件夹的内容的相关的信息。 查看文件夹位于邮件存储的根目录下，因此，不可见的典型的客户端应用程序中。 不是每个消息存储包括查看文件夹;仅配置为默认的邮件存储用作会话的消息存储必须包括它们。  
  
MAPI 支持两个视图文件夹：
  
- 常见 — 公共视图文件夹中包含的是标准的消息存储库的并且可供客户端访问的消息存储的任何用户视图。 存储在的存储**PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md)) 属性中的公共视图文件夹的项标识符。
    
- 个人 — 个人视图文件夹包含由特定用户定义的视图。 MAPI 定义按住个人视图文件夹的项标识符的**PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md)) 属性。 使用个人视图，例如，一个用户无法查看一组按发件人，列出仅邮件主题和回执日期; 的消息另一个用户无法查看同一组按日期排序，列出的主题、 发件人和邮件大小。
    
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

