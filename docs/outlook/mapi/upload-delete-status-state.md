---
title: 上传删除状态状态
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
# <a name="upload-delete-status-state"></a>上传删除状态状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的上载删除状态状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符:  <br/> |**LR_SYNC_UPLOAD_MESSAGE_DEL** <br/> |
|相关数据结构:  <br/> |**[UPDEL](updel.md)** <br/> |
|从此状态:  <br/> |[上传表状态](upload-table-state.md) <br/> |
|到此状态:  <br/> |上传表状态  <br/> |
   
> [!NOTE]
> 复制状态计算机是确定的状态机。 客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。 
  
## <a name="description"></a>说明

此状态会在服务器上启动更新, 这些 Outlook 项目 (邮件、日历、联系人、任务、便笺或日记) 已在以前的上载表状态中指定的本地存储上的文件夹中删除。 在此状态下, Outlook 使用已从文件夹中删除或移动的项目的信息初始化关联的**UPDEL**数据结构中的成员。 
  
然后, 客户端会删除服务器上的文件夹中的指定项。 若要区分已移动而不是已删除的项目, 客户端必须检查**UPDEL**结构中标识的*pupmov*成员。 
  
当此状态结束时, Outlook 将清除指示该项已被删除的内部信息;因此, Outlook 将不再具有该项目的记录。 本地存储将返回到上传表状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

