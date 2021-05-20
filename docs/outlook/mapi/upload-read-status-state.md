---
title: Upload读取状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4d45574e-df87-8c44-4aa7-d41b38406f0a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e8ad2acf019df3f07060c8e8c71a62afd3fca03c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431538"
---
# <a name="upload-read-status-state"></a>Upload读取状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的上载读取状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_UPLOAD_MESSAGE_READ** <br/> |
|相关数据结构：  <br/> |**[UPREAD](upread.md)** <br/> |
|从此状态：  <br/> |[Upload表状态](upload-table-state.md) <br/> |
|至此状态：  <br/> |Upload表状态  <br/> |
   
> [!NOTE]
> 复制状态机是一个确定性状态机。 从一个状态到另一个状态的客户端最终必须从后者返回到前者。 
  
## <a name="description"></a>说明

此状态将启动在先前上传表状态中指定的文件夹中上传项目的读取状态。 在此状态中，Outlook读取状态已更改的文件夹中的项目的信息初始化关联的 **UPREAD** 数据结构。 然后，客户端会在服务器上将这些项目的读取状态更新为已读或未读。 
  
此状态结束时，Outlook清除有关项目的读取状态的内部信息，以防止再次上载项目的读取状态。 本地存储将返回到上载表状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

