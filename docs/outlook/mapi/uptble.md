---
title: UPTBLE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f7fcb385-186d-d5fe-7104-fe0af09d5768
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d0b440f01aad7078ed76cd37d36c5ad506215438
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329706"
---
# <a name="uptble"></a>UPTBLE

**适用于**：Outlook 2013 | Outlook 2016 
  
[上载表状态](upload-table-state.md)期间上载文件夹内容的扩展信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPTBLE 
{ 
    UINTiEntMod; 
    UINTcEntMod; 
    UINTiEntRead; 
    UINTcEntRead; 
    UINTiEntDel; 
    UINTcEntDel; 
};
```

## <a name="members"></a>成员

 _iEntMod_
  
>  排除用于跟踪上载新项目或修改的项目的_cEntMod_数量的索引。 
    
 _cEntMod_
  
>  排除文件夹中新项目或修改项目的数量。 
    
 _iEntRead_
  
>  排除用于跟踪上载_cEntRead_读取项目数的索引。 
    
 _cEntRead_
  
>  排除文件夹中的已读项目数。 
    
 _iEntDel_
  
>  排除用于跟踪上载_cEntDel_已删除项目数的索引。 
    
 _cEntDel_
  
>  排除文件夹中已删除项目的数量。 
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md) 
- [关于复制状态机](about-the-replication-state-machine.md)
- [UPTBL](uptbl.md)

