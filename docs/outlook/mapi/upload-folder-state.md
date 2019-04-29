---
title: 上传文件夹状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 270b1df0-c5cd-0d0f-7b57-2726dee978ab
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c20f2998a2fef1ddb53b13708dcf56f9d7b50dbe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419567"
---
# <a name="upload-folder-state"></a>上传文件夹状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的上载文件夹状态过程中发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符:  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |
|相关数据结构:  <br/> |**[UPFLD](upfld.md)** <br/> |
|从此状态:  <br/> |[上传层次结构状态](upload-hierarchy-state.md) <br/> |
|到此状态:  <br/> |上传层次结构状态  <br/> |
   
> [!NOTE]
> 复制状态计算机是确定的状态机。 客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。 
  
## <a name="description"></a>说明

此状态将启动上传层次结构状态中指定的层次结构中的文件夹。 在此状态下, Outlook 提供的文件夹对象 (如果尚未删除) 和指示文件夹状态的标志 ("新建"、"已移动"、"已修改" 或 "已删除") 作为相应**UPFLD**数据结构的一部分。 然后, 客户端将此信息上载到服务器。 
  
如果上载成功, 客户端会将**UPFLD**中的*ulFlags*设置为**UPF_OK**。 然后, Outlook 清除其有关上载文件夹的请求的内部信息。 
  
文件夹上传结束时, 本地存储将返回到上传层次结构状态。 根据与上述上传层次结构状态相对应的**[UPHIER](uphier.md)** 结构, Outlook 决定是否继续上传下一个文件夹, 并准备下一个上载文件夹状态。 
  
> [!NOTE]
> 如果客户端只需要上传一个文件夹, 则客户端可以通过[同步状态](synchronize-state.md)启动复制, 而无需输入上传层次结构状态。 客户端将**[同步](sync.md)** 的某些成员 ( *ulFlags* to **UPS_UPLOAD_ONLY** and **UPS_ONE_FOLDER** and *feid* ) 设置为文件夹的 ID, 告诉 Outlook 只会上载一个文件夹。 
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

