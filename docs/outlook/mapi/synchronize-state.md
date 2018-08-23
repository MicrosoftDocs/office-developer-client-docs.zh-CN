---
title: 同步状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 270ff414-514c-b1fc-db48-761bf6de8867
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d9f2a11a9ec1691863b476fed02eff1831a69207
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569720"
---
# <a name="synchronize-state"></a>同步状态

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 本主题介绍时会发生什么情况期间的复制状态机同步状态。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC** <br/> |
|相关的数据结构：  <br/> |**[SYNC](sync.md)** <br/> |
|从此状态：  <br/> |[空闲状态](idle-state.md) <br/> |
|为此状态：  <br/> |[下载层次结构状态](download-hierarchy-state.md)、[同步内容状态](synchronize-contents-state.md)、[上载层次结构状态](upload-hierarchy-state.md)，或空闲状态  <br/> |
   
> [!NOTE]
> 复制状态机是确定性状态机。 从一种状态传出到另一个客户端从后者必须最终返回到前者。 
  
## <a name="description"></a>说明

此状态启动同步。 本地存储从此处可以转换为上载或下载状态。 例如，本地存储可以移到上载层次结构状态文件夹层次结构上载到服务器，或它可以执行完全同步的第一个上载层次结构，然后从服务器下载层次结构。
  
在此状态下，Outlook 初始化的本地存储的路径具有关联的**同步**数据结构，以便该 Outlook 其他状态期间看到修改。 
  
[输入] 设置客户端**同步**，其告知如何处理其他状态的 Outlook 的成员。 例如，客户端可以设置*ulFlags* **UPS_UPLOAD_ONLY**和**UPS_THESE_FOLDERS**和将上载*pel*以告知 Outlook 仅这些文件夹的文件夹的项标识符的列表。 此状态结束时，本地存储恢复到空闲状态。 
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

