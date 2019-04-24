---
title: 上传表状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: fe167c90-c817-b627-0728-5c6393477c22
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a2a9b3f214c76b8ec965c84c4731e0dc57e83352
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342838"
---
# <a name="upload-table-state"></a>上传表状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的上载表状态过程中发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符:  <br/> |**LR_SYNC_UPLOAD_TABLE** <br/> |
|相关数据结构:  <br/> |**[UPTBL](uptbl.md)** <br/> |
|从此状态:  <br/> |[同步内容状态](synchronize-contents-state.md) <br/> |
|到此状态:  <br/> |[上载邮件状态](upload-message-state.md)、[上载删除状态状态](upload-delete-status-state.md)、[上传阅读状态状态](upload-read-status-state.md)或同步内容状态  <br/> |
   
> [!NOTE]
> 复制状态计算机是确定的状态机。 客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。 
  
## <a name="description"></a>说明

此状态会启动上传之前的同步内容状态中指定的文件夹的内容。 文件夹可以是 "邮件"、"日历"、"联系人"、"任务"、"便笺" 或 "日记" 文件夹。 在此状态下, Outlook 将创建已添加、修改、移动、删除或标记为已读的项目列表, 并为相应的上传邮件状态、上传删除状态状态或上传阅读状态准备相应的内部信息。状态.
  
当此状态结束时, Outlook 会将文件夹标记为同步其内容, 以便在进行其他修改之前不会再次上载内容。 本地存储将返回到同步内容状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

