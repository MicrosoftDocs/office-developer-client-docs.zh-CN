---
title: 上传层次结构状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: e39c4198-4913-5e86-900a-32e5ba5d801c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f789f4d7bbaf585d0d80f2208c35313542dfc191
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415423"
---
# <a name="upload-hierarchy-state"></a>上传层次结构状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的上载层次结构状态过程中发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符:  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |
|相关数据结构:  <br/> |**[UPHIER](uphier.md)** <br/> |
|从此状态:  <br/> |[同步状态](synchronize-state.md) <br/> |
|到此状态:  <br/> |[上传文件夹状态](upload-folder-state.md)或同步状态  <br/> |
   
> [!NOTE]
> 复制状态计算机是确定的状态机。 客户端在向另一种状态传出一种状态时, 最终必须从后者返回前一个状态。 
  
## <a name="description"></a>说明

此状态将启动上载已在之前的同步状态中指定的文件夹树层次结构。 Outlook 确定在该层次结构中创建或修改的文件夹数, 并在**UPHIER**中初始化*分币*。 Outlook 还会保留上载的文件夹与其他成员*iEnt*的数量的计数。 若要上传每个*分币*文件夹, 客户端会将本地存储区移到上传文件夹状态, 并在文件夹上传完成时返回到上传层次结构状态。 
  
当上载层次结构状态结束时, 本地存储将返回到同步状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

