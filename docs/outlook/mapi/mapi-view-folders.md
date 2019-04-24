---
title: MAPI 视图文件夹
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a1936ec2-bf8a-4242-a41d-64d26b813bd0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ca9e5138d3ded13dfe33037f75e43ef1098f3c2d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357335"
---
# <a name="mapi-view-folders"></a>MAPI 视图文件夹

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
查看文件夹是包含相关信息的根文件夹, 用于定义人际邮件 (IPM) 文件夹的内容的替代显示布局。 View 文件夹驻留在邮件存储区的根目录下, 因此, 在典型的客户端应用程序中不可见。 并不是每个邮件存储都包含查看文件夹;只有配置为可用作会话的默认邮件存储的邮件存储必须包含它们。  
  
MAPI 支持两个视图文件夹:
  
- 常用视图文件夹包含为邮件存储库的标准视图, 可供访问邮件存储区的客户端的任何用户使用。 公用视图文件夹的条目标识符存储在存储的**PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md)) 属性中。
    
- 个人-"个人视图" 文件夹包含由特定用户定义的视图。 MAPI 定义了**PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md)) 属性, 用于保存个人视图文件夹的条目标识符。 例如, 使用个人视图, 一个用户可以查看按发件人排序的一组邮件, 仅列出邮件主题和接收日期;另一个用户可以查看按日期排序的相同组, 并列出主题、发件人和邮件大小。
    
## <a name="see-also"></a>另请参阅



[MAPI 文件夹](mapi-folders.md)

