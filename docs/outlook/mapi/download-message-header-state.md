---
title: 下载邮件头状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 03f69592-a5ea-e30b-9674-9cfa895163d8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c8e83119d724f583d40583a6a5227bc467dc94da
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338834"
---
# <a name="download-message-header-state"></a>下载邮件头状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的下载邮件头状态过程中发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符:  <br/> |**LR_SYNC_DOWNLOAD_HEADER** <br/> |
|相关数据结构:  <br/> |**[HDRSYNC](hdrsync.md)** <br/> |
|从此状态:  <br/> |[空闲状态](idle-state.md) <br/> |
|到此状态:  <br/> |空闲状态  <br/> |
   
> [!NOTE]
> 复制状态计算机是确定的状态机。 客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。 
  
## <a name="description"></a>说明

在此状态下, 客户端更新本地存储区上的邮件的邮件头。 本地存储在**[IOSTX:: SyncHdrBeg](iostx-synchdrbeg.md)** 时进入此状态, 并在调用**[IOSTX:: SyncHdrEnd](iostx-synchdrend.md)** 时退出。 在此状态下, Outlook 使用有关邮件标头的信息初始化关联的**HDRSYNC**数据结构的成员。 客户端先从服务器下载完整的邮件项, 然后在本地更新邮件项的邮件头。 
  
当同步结束时, 客户端会设置下载结果。 本地存储将返回到空闲状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

