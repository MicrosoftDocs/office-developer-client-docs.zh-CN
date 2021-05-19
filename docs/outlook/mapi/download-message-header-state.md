---
title: 下载邮件头状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 03f69592-a5ea-e30b-9674-9cfa895163d8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c8e83119d724f583d40583a6a5227bc467dc94da
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417117"
---
# <a name="download-message-header-state"></a>下载邮件头状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的下载邮件头状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_DOWNLOAD_HEADER** <br/> |
|相关数据结构：  <br/> |**[HDRSYNC](hdrsync.md)** <br/> |
|从此状态：  <br/> |[空闲状态](idle-state.md) <br/> |
|至此状态：  <br/> |空闲状态  <br/> |
   
> [!NOTE]
> 复制状态机是一个确定性状态机。 从一个状态到另一个状态的客户端最终必须从后者返回到前者。 
  
## <a name="description"></a>说明

在此状态中，客户端更新本地存储上的邮件头。 本地存储在 **[IOSTX：：SyncHdrBeg](iostx-synchdrbeg.md)** 上进入此状态，在 **[调用 IOSTX：：SyncHdrEnd](iostx-synchdrend.md)** 时退出。 在此状态中，Outlook使用有关邮件头的信息初始化关联的 **HDRSYNC** 数据结构的成员。 客户端首先从服务器下载完整邮件项目，然后在本地更新邮件项的标头。 
  
同步结束时，客户端将设置下载结果。 本地存储将返回到空闲状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

