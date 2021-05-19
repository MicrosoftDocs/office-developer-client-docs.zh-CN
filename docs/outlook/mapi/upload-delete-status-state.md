---
title: Upload删除状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: dee566ad-b46d-1015-4b0b-6c3313060142
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dda9d23a572446a5fa79a9500eb69558b6e0debd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425839"
---
# <a name="upload-delete-status-state"></a>Upload删除状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的上载删除状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_UPLOAD_MESSAGE_DEL** <br/> |
|相关数据结构：  <br/> |**[UPDEL](updel.md)** <br/> |
|从此状态：  <br/> |[Upload表状态](upload-table-state.md) <br/> |
|至此状态：  <br/> |Upload表状态  <br/> |
   
> [!NOTE]
> 复制状态机是一个确定性状态机。 从一个状态到另一个状态的客户端最终必须从后者返回到前者。 
  
## <a name="description"></a>说明

此状态将在服务器上启动更新Outlook (邮件、日历、联系人、任务、笔记或日记) 项目，这些项目已在先前上传表状态指定的本地存储上的文件夹中删除。 在此状态中，Outlook关联的 **UPDEL** 数据结构中的成员，并获取已删除或从文件夹中移动的项目的信息。 
  
然后，客户端将删除服务器上文件夹中的指定项目。 为了区分已移动而不是已删除的项目，客户端必须检查 **UPDEL** 结构中标识的 *pupmov* 成员。 
  
当此状态结束时，Outlook清除指示项目已删除的内部信息;因此，Outlook不再具有该项目的记录。 本地存储将返回到上载表状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

