---
title: 上传“删除状态”状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: dee566ad-b46d-1015-4b0b-6c3313060142
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4a45cfafec5126c72f365858e41963bc95fa707a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574543"
---
# <a name="upload-delete-status-state"></a>上传“删除状态”状态

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 本主题介绍的复制状态机上载删除状态状态期间出现的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_UPLOAD_MESSAGE_DEL** <br/> |
|相关的数据结构：  <br/> |**[UPDEL](updel.md)** <br/> |
|从此状态：  <br/> |[上载表状态](upload-table-state.md) <br/> |
|为此状态：  <br/> |上载表状态  <br/> |
   
> [!NOTE]
> 复制状态机是确定性状态机。 从一种状态传出到另一个客户端从后者必须最终返回到前者。 
  
## <a name="description"></a>说明

此状态启动服务器上更新已在前面的上载表状态中指定的本地存储区上的文件夹中删除这些 Outlook 项目 （邮件、 日历、 联系人、 任务、 注释或日志）。 在此状态下，Outlook 初始化信息的项目的已删除或从文件夹移关联**UPDEL**数据结构中的成员。 
  
然后，客户端删除的服务器上的文件夹中的指定的项。 为了区分已移动而不是具有已删除的项，客户端必须检查**UPDEL**结构中标识的*pupmov*成员。 
  
此状态结束时，Outlook 将清除指示已删除项目; 内部信息因此，Outlook 将不再能够项的记录。 本地存储返回到上载表状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

