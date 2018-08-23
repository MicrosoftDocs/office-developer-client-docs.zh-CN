---
title: UPDEL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3b23291d-3355-d772-4647-d4bbd64b0b53
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 057a1ff38ed3809ce03bce8f820f1d16eea7fb46
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581123"
---
# <a name="updel"></a>UPDEL

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
已删除本地存储区中的项目的信息。 [上载删除状态状态](upload-delete-status-state.md)期间使用此信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPDEL 
{ 
    PUPDELE pupde; 
    UINT cEnt; 
};
```

## <a name="members"></a>Members

 _pupde_
  
>  [输出][UPDELE](updele.md)条目的向量。 
    
 _%_
  
> [输出]*Pupde*中的条目数。 
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)

