---
title: UPHIER
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a75ca0dd-9c50-2a9f-6c59-1f8020833a01
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a1ec71d7120eab220ee3b11d2a751fba51cee48e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592092"
---
# <a name="uphier"></a>UPHIER
 
**适用于**： Outlook 2013 |Outlook 2016 
  
[上载层次结构状态](upload-hierarchy-state.md)期间同步文件夹层次结构的信息。
  
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

## <a name="members"></a>Members

_ulFlags_
  
> [in]要同步的文件夹层次结构时修改的行为的标志。
    
  - UPH_OK
    
    - [in]上载成功。 客户端设置此后成功上载到服务器的信息。 时看到此标志，Outlook 清除指定的文件夹层次结构需要更新任何内部记帐信息。 
    
    - 如果上载未成功，则客户端通过 HRESULT。
    
_pstmReserved_
  
> [输出]此成员仅供 Outlook 内部使用，不支持。
    
_iEnt_
  
> [输出]索引来跟踪同步 *%* 由指定的文件夹的数目。 
    
_%_
  
> [输出]文件夹的同步的数。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态计算机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)

