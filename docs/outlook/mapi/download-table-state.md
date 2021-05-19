---
title: 下载表状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5bcc8b0a-0ab7-6c3e-8334-9e83cf2882a7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7451d159ef97ef9d8160b386ec5bf88fb388706e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338337"
---
# <a name="download-table-state"></a>下载表状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的下载表状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_DOWNLOAD_TABLE** <br/> |
|相关数据结构：  <br/> |**[DNTBL](dntbl.md)** <br/> |
|从此状态：  <br/> |[同步内容状态](synchronize-contents-state.md) <br/> |
|至此状态：  <br/> |同步内容状态  <br/> |
   
> [!NOTE]
> 复制状态机是一个确定性状态机。 从一个状态到另一个状态的客户端最终必须从后者返回到前者。 
  
## <a name="description"></a>说明

此状态将启动下载文件夹。 在此状态中，Outlook文件夹相关信息初始化关联的 **DNTBL** 数据结构。 客户端下载文件夹内容，然后使用服务器中的新内容、修改或删除更新本地存储上的文件夹。 下载过程采用 Microsoft Exchange 增量更改同步 (ICS) 。 有关 ICS 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
  
当此状态结束时，本地存储将返回同步内容状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

