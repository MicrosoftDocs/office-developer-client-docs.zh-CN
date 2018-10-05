---
title: 下载层次结构状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8e0400ba-8530-e6ac-5de8-a62aeec5e10a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 45535eef75c6fc091c02ec35b669675a51e4cf48
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384855"
---
# <a name="download-hierarchy-state"></a>下载层次结构状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍的复制状态机下载层次结构状态期间出现的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_DOWNLOAD_HIERARCHY** <br/> |
|相关的数据结构：  <br/> |**[DNHIER](dnhier.md)** <br/> |
|从此状态：  <br/> |[同步状态](synchronize-state.md) <br/> |
|为此状态：  <br/> |同步状态  <br/> |
   
> [!NOTE]
> 复制状态机是确定性状态机。 从一种状态传出到另一个客户端从后者必须最终返回到前者。 
  
## <a name="description"></a>说明

此状态启动到本地存储从服务器下载文件夹树层次结构。 
  
Outlook 初始化的层次结构的指针具有关联的**DNHIER**数据结构。 客户端下载层次结构，并将本地存储插入新的文件夹或文件夹的修改。 下载过程采用 Microsoft Exchange 增量更改同步 (ICS)。 ICS 的详细信息，请参阅[ICS 评价标准](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
  
此状态结束时，本地存储返回到同步状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

