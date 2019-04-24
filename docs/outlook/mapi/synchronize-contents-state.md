---
title: 同步内容状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 52216bc3-8cbd-3856-ea46-78f7d0dd66ff
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ebe1f5f48f9becdf01ea184c2b76fa2c8fa21e8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349565"
---
# <a name="synchronize-contents-state"></a>同步内容状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍在复制状态机的同步内容状态期间会发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符:  <br/> |**LR_SYNC_CONTENTS** <br/> |
|相关数据结构:  <br/> |**[SYNCCONT](synccont.md)** <br/> |
|从此状态:  <br/> |[同步状态](synchronize-state.md) <br/> |
|到此状态:  <br/> |[下载表状态](download-table-state.md)、[上传表状态](upload-table-state.md)或同步状态  <br/> |
   
> [!NOTE]
> 复制状态计算机是确定的状态机。 客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。 
  
## <a name="description"></a>说明

此状态将启动两个复制过程之一: 上载本地存储上指定文件夹的内容或完全同步。 在完全同步中, 对于每个指定的文件夹, 首先上载并下载内容。 根据上一同步状态中对应**[同步](sync.md)** 结构中设置的*ulFlags* , Outlook 将初始化**SYNCCONT**结构中的 [out] 成员以提供有关内容的信息。 
  
通过相同的**SYNCCONT**结构, 客户端可以获取包含要上载或下载的内容的文件夹的计数。 客户端将通过以下方式遍历这些文件夹中的每一个: 将本地存储移动到上载表状态以上载文件夹, 或将本地存储移动到下载表状态以下载该文件夹。 
  
此外, 客户端还获取需要复制的文件夹的条目 id。
  
当此状态结束时, Outlook 将清除其内部信息。 本地存储将返回到同步状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

