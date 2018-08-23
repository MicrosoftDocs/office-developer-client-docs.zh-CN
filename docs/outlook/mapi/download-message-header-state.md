---
title: 下载邮件头状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 03f69592-a5ea-e30b-9674-9cfa895163d8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c9d1745d25e7f7a5052d767350ade6723067d1b8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578841"
---
# <a name="download-message-header-state"></a>下载邮件头状态

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 本主题介绍在下载邮件头状态的复制状态机时发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_DOWNLOAD_HEADER** <br/> |
|相关的数据结构：  <br/> |**[HDRSYNC](hdrsync.md)** <br/> |
|从此状态：  <br/> |[空闲状态](idle-state.md) <br/> |
|为此状态：  <br/> |空闲状态  <br/> |
   
> [!NOTE]
> 复制状态机是确定性状态机。 从一种状态传出到另一个客户端从后者必须最终返回到前者。 
  
## <a name="description"></a>说明

在此状态下，客户端更新本地存储区上的邮件的标头。 本地存储进入**[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)** 时此状态，并在调用**[IOSTX::SyncHdrEnd](iostx-synchdrend.md)** 时退出。 在此状态下，Outlook 初始化信息的邮件的标头关联**HDRSYNC**数据结构的成员。 客户端首次从服务器下载完整邮件项目，然后更新本地的邮件项目的标题。 
  
同步结束时，客户端设置下载结果。 本地存储返回到空闲状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

