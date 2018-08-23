---
title: 上传文件夹状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 270b1df0-c5cd-0d0f-7b57-2726dee978ab
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ae8c3c4012874e1ca35761b103066cceebb1b165
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576748"
---
# <a name="upload-folder-state"></a>上传文件夹状态

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 本主题介绍的复制状态机上载文件夹状态期间出现的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |
|相关的数据结构：  <br/> |**[UPFLD](upfld.md)** <br/> |
|从此状态：  <br/> |[上载层次结构状态](upload-hierarchy-state.md) <br/> |
|为此状态：  <br/> |上载层次结构状态  <br/> |
   
> [!NOTE]
> 复制状态机是确定性状态机。 从一种状态传出到另一个客户端从后者必须最终返回到前者。 
  
## <a name="description"></a>说明

此状态启动上载已指定为上述上载层次结构状态层次结构中的文件夹。 在此状态下，Outlook 提供文件夹对象 （如果它不被删除） 和相应**UPFLD**数据结构的一部分指示文件夹 （新建、 移动、 修改或删除） 的状态标志。 然后，客户端将此信息上载到服务器。 
  
如果成功上载，客户端设置到**UPF_OK** **UPFLD** *ulFlags* 。 Outlook 然后再清除其内部上载文件夹的请求信息。 
  
文件夹上载结束时，本地存储返回到上载层次结构状态。 基于**[UPHIER](uphier.md)** 结构对应于上述上载层次结构状态，Outlook 来确定是否要继续进行上载下一步文件夹，并为下一个上载文件夹状态准备。 
  
> [!NOTE]
> 如果客户端需要上载只有一个文件夹，客户端可以发起通过[同步状态](synchronize-state.md)复制，无需输入上载层次结构状态。 客户端设置**[同步](sync.md)** 的特定成员 — *ulFlags* **UPS_UPLOAD_ONLY**和**UPS_ONE_FOLDER**以及为该文件夹的 ID *feid* — 以告知该只有一个文件夹的 Outlook 将上载。 
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

