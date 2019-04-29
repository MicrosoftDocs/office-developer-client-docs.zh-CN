---
title: 上载读取状态状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4d45574e-df87-8c44-4aa7-d41b38406f0a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e8ad2acf019df3f07060c8e8c71a62afd3fca03c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431538"
---
# <a name="upload-read-status-state"></a>上载读取状态状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的上载读取状态状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符:  <br/> |**LR_SYNC_UPLOAD_MESSAGE_READ** <br/> |
|相关数据结构:  <br/> |**[UPREAD](upread.md)** <br/> |
|从此状态:  <br/> |[上传表状态](upload-table-state.md) <br/> |
|到此状态:  <br/> |上传表状态  <br/> |
   
> [!NOTE]
> 复制状态计算机是确定的状态机。 客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。 
  
## <a name="description"></a>说明

此状态将启动上传表状态中指定的文件夹中项目的读取状态的上载。 在此状态下, Outlook 将关联的**UPREAD**数据结构与已更改其读取状态的文件夹中的项目的信息进行初始化。 然后, 客户端将服务器上这些项目的读取状态更新为 "已读" 或 "未读"。 
  
当此状态结束时, Outlook 将清除有关项目读取状态的内部信息, 以防止再次上载项目的读取状态。 本地存储将返回到上传表状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

