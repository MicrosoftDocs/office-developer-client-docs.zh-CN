---
title: 下载层次结构状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8e0400ba-8530-e6ac-5de8-a62aeec5e10a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 45535eef75c6fc091c02ec35b669675a51e4cf48
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337007"
---
# <a name="download-hierarchy-state"></a>下载层次结构状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍复制状态机的下载层次结构状态期间发生的情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_DOWNLOAD_HIERARCHY** <br/> |
|相关数据结构：  <br/> |**[DNHIER](dnhier.md)** <br/> |
|从此状态：  <br/> |[同步状态](synchronize-state.md) <br/> |
|至此状态：  <br/> |同步状态  <br/> |
   
> [!NOTE]
> 复制状态机是一个确定性状态机。 从一个状态到另一个状态的客户端最终必须从后者返回到前者。 
  
## <a name="description"></a>说明

此状态启动将文件夹的树层次结构从服务器下载到本地存储。 
  
Outlook一个指向层次结构的指针初始化关联的 **DNHIER** 数据结构。 客户端下载层次结构，并将新文件夹或修改插入到本地存储中的文件夹。 下载过程采用 Microsoft Exchange 增量更改同步 (ICS) 。 有关 ICS 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
  
当此状态结束时，本地存储将返回到同步状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

