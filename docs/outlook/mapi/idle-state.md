---
title: 空闲状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 46976bea-c6bb-2e37-2e67-4cbccaa03aec
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3db4ead7e2485bbbae82f2a07659c934b394d6d5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419476"
---
# <a name="idle-state"></a>空闲状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 本主题介绍在复制状态机的空闲状态期间会发生什么情况。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|状态标识符：  <br/> |**LR_SYNC_IDLE** <br/> |
|相关数据结构：  <br/> | *无*  <br/> |
|从此状态：  <br/> | *不适用*  <br/> |
|至此状态：  <br/> |[同步状态](synchronize-state.md) <br/> |
   
> [!NOTE]
> 复制状态机是一个确定性状态机。 从一个状态到另一个状态的客户端最终必须从后者返回到前者。 
  
## <a name="description"></a>说明

在此状态中不执行任何操作。 本地存储在启动复制之前和复制完成之后都在此状态。
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[SYNCSTATE](syncstate.md)

