---
title: Upload表状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: fe167c90-c817-b627-0728-5c6393477c22
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a2a9b3f214c76b8ec965c84c4731e0dc57e83352
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405819"
---
# <a name="upload-table-state"></a>Upload表状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的上载表状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_UPLOAD_TABLE** <br/> |
|相关数据结构：  <br/> |**[UPTBL](uptbl.md)** <br/> |
|从此状态：  <br/> |[同步内容状态](synchronize-contents-state.md) <br/> |
|至此状态：  <br/> |[Upload邮件状态、](upload-message-state.md)[上传删除状态、](upload-delete-status-state.md)[上传读取状态或](upload-read-status-state.md)同步内容状态  <br/> |
   
> [!NOTE]
> 复制状态机是一个确定性状态机。 从一个状态到另一个状态的客户端最终必须从后者返回到前者。 
  
## <a name="description"></a>说明

此状态将启动上载之前同步内容状态中指定的文件夹的内容。 该文件夹可以是邮件、日历、联系人、任务、便笺或日记文件夹。 在此状态中，Outlook创建已添加、修改、移动、删除或标记为已读的项目列表，并为相应的上传邮件状态、上传删除状态或上传读取状态状态准备相应的内部信息。
  
当此状态结束时，Outlook将文件夹标记为已同步其内容，以便内容不会再次上载，直到进行其他修改。 本地存储将返回同步内容状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

