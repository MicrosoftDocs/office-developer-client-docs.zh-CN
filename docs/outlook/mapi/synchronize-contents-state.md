---
title: 同步内容状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 52216bc3-8cbd-3856-ea46-78f7d0dd66ff
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ebe1f5f48f9becdf01ea184c2b76fa2c8fa21e8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438468"
---
# <a name="synchronize-contents-state"></a>同步内容状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍同步复制状态机的内容状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_CONTENTS** <br/> |
|相关数据结构：  <br/> |**[SYNCCONT](synccont.md)** <br/> |
|从此状态：  <br/> |[同步状态](synchronize-state.md) <br/> |
|至此状态：  <br/> |[下载表状态](download-table-state.md)[、上传表状态](upload-table-state.md)或同步状态  <br/> |
   
> [!NOTE]
> 复制状态机是一个确定性状态机。 从一个状态到另一个状态的客户端最终必须从后者返回到前者。 
  
## <a name="description"></a>说明

此状态启动两个复制过程之一：在本地存储上上载指定文件夹的内容或完全同步。 在完全同步中，将首先上传并下载每个指定文件夹的内容。 根据前面同步状态的相应 **[SYNC](sync.md)** 结构中设置的 *ulFlags，Outlook* **SYNCCONT** 结构中初始化 [out] 成员以提供内容相关信息。 
  
通过相同的 **SYNCCONT** 结构，客户端获取包含要上载或下载的内容的文件夹计数。 客户端将循环访问其中每个文件夹，方法为将本地存储移动到上传表状态以上传文件夹，或将本地存储移动到下载表状态以下载文件夹。 
  
此外，客户端获取需要复制的文件夹的条目 ID。
  
当此状态结束时，Outlook清理其内部信息。 本地存储将返回到同步状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

