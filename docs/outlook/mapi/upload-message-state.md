---
title: Upload邮件状态
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
# <a name="upload-message-state"></a>Upload邮件状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍在复制状态机的上载邮件状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_UPLOAD_MESSAGE** <br/> |
|相关数据结构：  <br/> |**[UPMSG](upmsg.md)** <br/> |
|从此状态：  <br/> |[Upload表状态](upload-table-state.md) <br/> |
|至此状态：  <br/> |Upload表状态  <br/> |
   
> [!NOTE]
> 复制状态机是一个确定性状态机。 从一个状态到另一个状态的客户端最终必须从后者返回到前者。 
  
## <a name="description"></a>说明

此状态将Outlook项目 (邮件、日历、联系人、任务、便笺或日记) 该邮件、日历、联系人、便笺或日记) 是新项或已移动到当前文件夹或已修改的项目。 Outlook添加、移动或修改项目时，使用相应信息初始化 correpsonding **UPMSG** 数据结构。 
  
如果已添加或移动项目，则客户端会适当地在服务器上添加或更新该项目。 
  
如果项目已修改，Outlook在 **UPMSG** 数据结构中进一步指定修改是位于邮件头 (在这种情况下，该项目是邮件头) 、项目属性中，还是项目本身需要解决冲突。 然后，客户端将更新服务器上项。 
  
项目上载结束时，Outlook消息已上载，因此不会在后续上载中处理邮件。 本地存储将返回到上载表状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

