---
title: 同步状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 270ff414-514c-b1fc-db48-761bf6de8867
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7abbf049a848d417f640528e5030e37a954413e5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414625"
---
# <a name="synchronize-state"></a>同步状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的同步状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC** <br/> |
|相关数据结构：  <br/> |**[SYNC](sync.md)** <br/> |
|从此状态：  <br/> |[空闲状态](idle-state.md) <br/> |
|至此状态：  <br/> |[下载层次结构状态](download-hierarchy-state.md)[、同步内容状态](synchronize-contents-state.md)、[上载层次结构状态](upload-hierarchy-state.md)或空闲状态  <br/> |
   
> [!NOTE]
> 复制状态机是一个确定性状态机。 从一个状态到另一个状态的客户端最终必须从后者返回到前者。 
  
## <a name="description"></a>说明

此状态将启动同步。 本地应用商店可以从此处转换为上传或下载状态。 例如，本地存储可以移动到上载层次结构状态以将文件夹层次结构上载到服务器，或者可以通过先上载层次结构然后从服务器下载层次结构来执行完全同步。
  
在此状态中，Outlook使用本地存储的路径初始化关联的 **SYNC** 数据结构，以便Outlook状态期间看到修改。 
  
客户端设置 **SYNC** 的 [in] 成员，Outlook如何处理其他状态。 例如，客户端可以将 *ulFlags* 设置为 **UPS_UPLOAD_ONLY** 和 **UPS_THESE_FOLDERS** 并拼写到文件夹的条目标识符列表，以告知 Outlook将仅上载这些文件夹。 当此状态结束时，本地存储将恢复为空闲状态。 
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

