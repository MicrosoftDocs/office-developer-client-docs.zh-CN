---
title: Upload层次结构状态
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
# <a name="upload-hierarchy-state"></a>Upload层次结构状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍在复制状态机的上载层次结构状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |
|相关数据结构：  <br/> |**[UPHIER](uphier.md)** <br/> |
|从此状态：  <br/> |[同步状态](synchronize-state.md) <br/> |
|至此状态：  <br/> |[Upload文件夹状态或](upload-folder-state.md)同步状态  <br/> |
   
> [!NOTE]
> 复制状态机是一个确定性状态机。 从一个状态到另一个状态的客户端最终必须从后者返回到另一个状态。 
  
## <a name="description"></a>说明

此状态启动上载在之前的同步状态中指定的文件夹树层次结构。 Outlook确定已在该层次结构中创建或修改的文件夹数，并初始化 **UPHIER** 中的 *cEnt。* Outlook还保留与另一个成员 iEnt 的已上传文件夹 *数的计数*。 若要上载每个  *cEnt*  文件夹，客户端会将本地存储移动到上载文件夹状态，在文件夹上载完成时返回到上载层次结构状态。 
  
当上载层次结构状态结束时，本地存储将返回到同步状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

