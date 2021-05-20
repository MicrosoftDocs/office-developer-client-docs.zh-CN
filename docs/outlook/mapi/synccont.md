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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430404"
---
# <a name="synccont"></a>SYNCCONT

**适用于**：Outlook 2013 | Outlook 2016 
  
有关在同步内容状态期间将本地存储中指定文件夹的内容与服务器 [同步的信息](synchronize-contents-state.md)。 这仅涉及上载，或涉及上载和下载的完全同步。
  
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
  
> [in]用于确定同步期间的适当行为的标志。
    
  - UPC_OK
    
  - [in]Upload同步或完全同步成功。 客户端在将信息与服务器同步后进行设置。
    
_iEnt_
  
> [out]索引，跟踪同步 cEnt 指定的文件夹数量  _中的内容_。
    
_cEnt_
  
> [out]要复制的文件夹数。
    
_pvReserved_
  
> 此成员仅供内部使用，Outlook不支持。 
    
_ptagaReserved_
  
> 此成员仅供内部使用，Outlook不支持。 
    
_psosReserved_
  
> 此成员仅供内部使用，Outlook不支持。 
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)

