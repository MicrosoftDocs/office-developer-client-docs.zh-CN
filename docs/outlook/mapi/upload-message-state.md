---
title: 上传邮件状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7fdc1494-4f40-38bd-d363-144ca70e5906
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 61cda23557a501a2651385d192f1dc7432ef1cb5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433799"
---
# <a name="upload-message-state"></a>上传邮件状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的上载邮件状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符:  <br/> |**LR_SYNC_UPLOAD_MESSAGE** <br/> |
|相关数据结构:  <br/> |**[UPMSG](upmsg.md)** <br/> |
|从此状态:  <br/> |[上传表状态](upload-table-state.md) <br/> |
|到此状态:  <br/> |上传表状态  <br/> |
   
> [!NOTE]
> 复制状态计算机是确定的状态机。 客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。 
  
## <a name="description"></a>说明

此状态会启动上载新的 Outlook 项目 (邮件、日历、联系人、任务、便笺或日记), 或者已被移动到当前文件夹或已修改的项目。 Outlook 使用项目的添加、移动或修改的相应信息初始化 correpsonding **UPMSG**数据结构。 
  
如果已添加或移动该项目, 则客户端会适当地在服务器上添加或更新项目。 
  
如果修改了项目, Outlook 会进一步在**UPMSG**数据结构中指定所做的修改是在邮件头中 (在这种情况下, 该项目是邮件头)、项目属性中还是在需要冲突的项本身中。办法. 然后, 客户端更新服务器上的项目。 
  
项目上传结束时, Outlook 会注意到邮件已上载, 因此在后续上传时不会处理该邮件。 本地存储将返回到上传表状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

