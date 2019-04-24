---
title: UPHIER
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a75ca0dd-9c50-2a9f-6c59-1f8020833a01
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 45ef7ce9291376ac020035f0bde6172caf6cc01b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359421"
---
# <a name="uphier"></a>UPHIER
 
**适用于**：Outlook 2013 | Outlook 2016 
  
用于在[上载层次结构状态](upload-hierarchy-state.md)期间同步文件夹层次结构的信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPHIER 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    UINT iEnt; 
    UINT cEnt; 
};
```

## <a name="members"></a>成员

_ulFlags_
  
> 实时用于在同步文件夹层次结构时修改行为的标志。
    
  - UPH_OK
    
    - 实时上载成功。 在成功将信息上载到服务器后, 客户端会对此进行设置。 在看到此标志之后, Outlook 将清除所有指示文件夹层次结构需要更新的内部簿记信息。 
    
    - 如果上载未成功, 客户端将传递 HRESULT。
    
_pstmReserved_
  
> 排除此成员保留供 Outlook 内部使用, 不受支持。
    
_iEnt_
  
> 排除用于跟踪对由*分币*指定的文件夹数进行同步的索引。 
    
_分币_
  
> 排除不同步的文件夹数。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)

