---
title: 同步内容状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 52216bc3-8cbd-3856-ea46-78f7d0dd66ff
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a2bdbeb39cce1e62569f364875c3828cdd530c63
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577245"
---
# <a name="synchronize-contents-state"></a>同步内容状态

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 本主题介绍的复制状态机同步内容状态期间出现的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_CONTENTS** <br/> |
|相关的数据结构：  <br/> |**[SYNCCONT](synccont.md)** <br/> |
|从此状态：  <br/> |[同步状态](synchronize-state.md) <br/> |
|为此状态：  <br/> |[下载表状态](download-table-state.md)、[上载表状态](upload-table-state.md)，或同步状态  <br/> |
   
> [!NOTE]
> 复制状态机是确定性状态机。 从一种状态传出到另一个客户端从后者必须最终返回到前者。 
  
## <a name="description"></a>说明

此状态启动两个复制过程之一： 上载的内容文件夹的本地存储区或指定完全同步。 在完全同步，为每个指定文件夹中，内容是首先上载和下载。 根据在上述的相应**[同步](sync.md)** 结构中设置*ulFlags*同步状态时，Outlook 初始化 [输出] **SYNCCONT**结构中的成员以提供有关内容的信息。 
  
通过相同的**SYNCCONT**结构，客户端获取具有内容上载或下载的文件夹的计数。 将本地存储移动到上载表状态上载一个文件夹，或移动到下载表状态，若要下载该文件夹的本地存储的情况下，客户端将循环访问每个这些文件夹。 
  
此外，客户端获取需要复制的文件夹的条目 Id。
  
此状态结束时，Outlook 将清理其内部的信息。 本地存储返回到同步状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

