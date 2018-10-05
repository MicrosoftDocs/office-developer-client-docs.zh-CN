---
title: 下载表状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5bcc8b0a-0ab7-6c3e-8334-9e83cf2882a7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7451d159ef97ef9d8160b386ec5bf88fb388706e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395068"
---
# <a name="download-table-state"></a>下载表状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍的复制状态机下载表状态期间出现的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_DOWNLOAD_TABLE** <br/> |
|相关的数据结构：  <br/> |**[DNTBL](dntbl.md)** <br/> |
|从此状态：  <br/> |[同步内容状态](synchronize-contents-state.md) <br/> |
|为此状态：  <br/> |同步内容状态  <br/> |
   
> [!NOTE]
> 复制状态机是确定性状态机。 从一种状态传出到另一个客户端从后者必须最终返回到前者。 
  
## <a name="description"></a>说明

此状态启动下载文件夹。 在此状态下，Outlook 初始化有关该文件夹具有关联的**DNTBL**数据结构。 客户端下载文件夹内容，并使用新的内容、 相应的修改或从服务器删除更新上本地存储的文件夹。 下载过程采用 Microsoft Exchange 增量更改同步 (ICS)。 ICS 的详细信息，请参阅[ICS 评价标准](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
  
此状态结束时，本地存储返回到同步内容状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

