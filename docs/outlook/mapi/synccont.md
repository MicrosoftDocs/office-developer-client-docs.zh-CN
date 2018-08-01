---
title: SYNCCONT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 7b4307a3-5a8c-89bf-1113-2549556a7fe7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 82923895353cf600c4d0b78b9a6e16fc7d57e466
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778927"
---
# <a name="synccont"></a>SYNCCONT

**适用于**： Outlook 
  
将本地存储区中的指定文件夹的内容与服务器同步过程中[同步内容状态](synchronize-contents-state.md)信息。 此步骤需要刚刚上载或涉及上载，然后选择下载的完全同步。
  
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

## <a name="members"></a>Members

_ulFlags_
  
> [in]同步过程中确定适当的行为的标志。
    
  - UPC_OK
    
  - [in]上载或完全同步成功。 客户端与服务器同步信息后设置此。
    
_iEnt_
  
> [输出]要跟踪同步中的 _%_ 由指定的文件夹的数量的内容索引。
    
_%_
  
> [输出]要复制的文件夹的数量。
    
_pvReserved_
  
> 此成员仅供内部使用的 Outlook，不支持。 
    
_ptagaReserved_
  
> 此成员仅供内部使用的 Outlook，不支持。 
    
_psosReserved_
  
> 此成员仅供内部使用的 Outlook，不支持。 
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态计算机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)

