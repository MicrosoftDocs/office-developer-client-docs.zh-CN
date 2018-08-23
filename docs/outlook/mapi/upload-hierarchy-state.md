---
title: 上传层次结构状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: e39c4198-4913-5e86-900a-32e5ba5d801c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ed24682086556addf76b8451674a73bd82ce050
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572184"
---
# <a name="upload-hierarchy-state"></a>上传层次结构状态

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 本主题介绍的复制状态机上载层次结构状态期间出现的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |
|相关的数据结构：  <br/> |**[UPHIER](uphier.md)** <br/> |
|从此状态：  <br/> |[同步状态](synchronize-state.md) <br/> |
|为此状态：  <br/> |[上载文件夹状态](upload-folder-state.md)，或同步状态  <br/> |
   
> [!NOTE]
> 复制状态机是确定性状态机。 传出到另一种状态的客户端从后者必须最终返回到前者。 
  
## <a name="description"></a>说明

此状态启动上载已在前面指定的文件夹树层次结构同步状态。 Outlook 来确定已创建或修改在该层次结构和初始化 *%uphier* **** 中的文件夹的数目。 同样，outlook 将保持与另一个成员*iEnt*上载文件夹的数目。 若要上载 *%* 文件夹中每个，客户端进入本地存储上载文件夹状态，文件夹上载完成后，返回到上载层次结构状态。 
  
上载层次结构状态结束时，本地存储返回到同步状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

