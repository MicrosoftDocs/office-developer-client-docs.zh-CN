---
title: Upload文件夹状态
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
# <a name="upload-folder-state"></a>Upload文件夹状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的上载文件夹状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |
|相关数据结构：  <br/> |**[UPFLD](upfld.md)** <br/> |
|从此状态：  <br/> |[Upload层次结构状态](upload-hierarchy-state.md) <br/> |
|至此状态：  <br/> |Upload层次结构状态  <br/> |
   
> [!NOTE]
> 复制状态机是一个确定性状态机。 从一个状态到另一个状态的客户端最终必须从后者返回到前者。 
  
## <a name="description"></a>说明

此状态启动在先前上载层次结构状态中指定的层次结构中上载文件夹。 在此状态中，Outlook 会提供文件夹对象 (（如果尚未删除) ）以及指示文件夹 (作为相应 **UPFLD** 数据结构一部分的新、移动、修改或删除) 的状态的标志。 然后，客户端将此信息上载到服务器。 
  
如果上载成功，客户端将 **UPFLD** 中的 *ulFlags* **UPF_OK。** Outlook然后清除其有关上载文件夹的请求的内部信息。 
  
当文件夹上载结束时，本地存储将返回到上载层次结构状态。 根据与上述上载层次结构状态对应的 **[UPHIER](uphier.md)** 结构，Outlook确定是否继续上载下一个文件夹并准备下一个上载文件夹状态。 
  
> [!NOTE]
> 如果客户端只需要上载一个文件夹，则客户端可以通过同步状态启动复制，而无需进入[](synchronize-state.md)上载层次结构状态。 客户端将 **[SYNC](sync.md)** 的某些成员 *（ulFlags*  UPS_UPLOAD_ONLY 和 **UPS_ONE_FOLDER** 和 *feid* 都设置到文件夹 ID）Outlook告知用户只会上载一个文件夹。 
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

