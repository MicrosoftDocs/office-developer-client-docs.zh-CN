---
title: 上传“读取状态”状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4d45574e-df87-8c44-4aa7-d41b38406f0a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 41815a88fe1215d2a85a38592e04b0d0bbd43cc6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573045"
---
# <a name="upload-read-status-state"></a>上传“读取状态”状态

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 本主题介绍上载读取的复制状态机状态状态期间出现的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_UPLOAD_MESSAGE_READ** <br/> |
|相关的数据结构：  <br/> |**[UPREAD](upread.md)** <br/> |
|从此状态：  <br/> |[上载表状态](upload-table-state.md) <br/> |
|为此状态：  <br/> |上载表状态  <br/> |
   
> [!NOTE]
> 复制状态机是确定性状态机。 从一种状态传出到另一个客户端从后者必须最终返回到前者。 
  
## <a name="description"></a>说明

此状态启动上载读取中前面的上载表状态指定文件夹中的项目的状态。 在此状态下，Outlook 初始化为其读取的状态已更改的文件夹中的那些项目的信息的关联的**UPREAD**数据结构。 然后，客户端更新读取为读或未读的服务器上对这些项目的状态。 
  
此状态结束时，Outlook 将清除的内部的项读取状态信息防止再次上载的项读取的状态。 本地存储返回到上载表状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

