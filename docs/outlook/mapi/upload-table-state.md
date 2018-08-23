---
title: 上传表状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: fe167c90-c817-b627-0728-5c6393477c22
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bd54c30e8701a13637235e28ddcfef4c21d10a2b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576979"
---
# <a name="upload-table-state"></a>上传表状态

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 本主题介绍的复制状态机上载表状态期间出现的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_UPLOAD_TABLE** <br/> |
|相关的数据结构：  <br/> |**[UPTBL](uptbl.md)** <br/> |
|从此状态：  <br/> |[同步内容状态](synchronize-contents-state.md) <br/> |
|为此状态：  <br/> |[上载邮件状态](upload-message-state.md)、[上载删除状态状态](upload-delete-status-state.md)、[上载读取状态状态](upload-read-status-state.md)，或同步内容状态  <br/> |
   
> [!NOTE]
> 复制状态机是确定性状态机。 从一种状态传出到另一个客户端从后者必须最终返回到前者。 
  
## <a name="description"></a>说明

此状态启动上载已在前面的同步内容状态指定文件夹的内容。 文件夹可以是邮件、 日历、 联系人、 任务、 备注或日记文件夹。 在此状态下，Outlook 创建列表项的已添加、 修改、 移动、 删除或标记为已读，并准备对应的上载邮件状态的适当内部信息、 上载删除状态状态或上载读取状态状态。
  
此状态结束时，Outlook 将标记为具有同步，其内容，以便进行另一种修改之前，内容将不重新上载的文件夹。 本地存储返回到同步内容状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

