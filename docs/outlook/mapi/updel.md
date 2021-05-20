---
title: UPDEL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3b23291d-3355-d772-4647-d4bbd64b0b53
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c9d2ec7f1970e3d1cadb65ab9af360b5c01c6844
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436796"
---
# <a name="updel"></a>UPDEL

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本地存储中已删除的项目的信息。 此信息在上载删除 [状态期间使用](upload-delete-status-state.md)。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPDEL 
{ 
    PUPDELE pupde; 
    UINT cEnt; 
};
```

## <a name="members"></a>成员

 _pupde_
  
>  [out] [UPDELE 条目](updele.md) 的矢量。 
    
 _cEnt_
  
> [out]  *pupde 中的条目数*  。 
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)

