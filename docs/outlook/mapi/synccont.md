---
title: SYNCCONT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 7b4307a3-5a8c-89bf-1113-2549556a7fe7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: afba7fa718a35d33966d45289461313e349ef2e2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349572"
---
# <a name="synccont"></a>SYNCCONT

**适用于**：Outlook 2013 | Outlook 2016 
  
[同步内容状态](synchronize-contents-state.md)期间, 用于将本地存储区中指定文件夹的内容与服务器同步的信息。 这只涉及上载或涉及上载的完全同步, 然后进行下载。
  
## <a name="quick-info"></a>快速信息

```cpp
struct SYNCCONT 
{ 
   ULONG   ulFlags; 
   UINT   iEnt; 
   UINT   cEnt; 
   LPVOID    pvReserved; 
   LPSPropTagArray   ptagaReserved; 
   LPSSortOrderSet   psosReserved; 
};
```

## <a name="members"></a>成员

_ulFlags_
  
> 实时用于确定同步过程中的相应行为的标志。
    
  - UPC_OK
    
  - 实时上载或完全同步成功。 客户端在将信息与服务器同步之后对此进行设置。
    
_iEnt_
  
> 排除索引以跟踪由_分币_指定的文件夹数中的内容同步。
    
_分币_
  
> 排除要复制的文件夹数。
    
_pvReserved_
  
> 此成员是为内部使用 Outlook 而保留的, 不受支持。 
    
_ptagaReserved_
  
> 此成员是为内部使用 Outlook 而保留的, 不受支持。 
    
_psosReserved_
  
> 此成员是为内部使用 Outlook 而保留的, 不受支持。 
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)

