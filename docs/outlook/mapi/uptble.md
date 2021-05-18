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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413838"
---
# <a name="uptble"></a>UPTBLE

**适用于**：Outlook 2013 | Outlook 2016 
  
上传表状态期间上传文件夹 [内容的扩展信息](upload-table-state.md)。
  
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
  
>  [out]跟踪新项或修改项  _的 cEntMod_ 数的上载的索引。 
    
 _cEntMod_
  
>  [out]文件夹中新项或修改的项目数。 
    
 _iEntRead_
  
>  [out]跟踪 cEntRead 读取项  _数的上载的_ 索引。 
    
 _cEntRead_
  
>  [out]文件夹中的读取项目数。 
    
 _iEntDel_
  
>  [out]跟踪  _cEntDel_ 已删除项目数的上载的索引。 
    
 _cEntDel_
  
>  [out]文件夹中已删除项目的数量。 
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md) 
- [关于复制状态机](about-the-replication-state-machine.md)
- [UPTBL](uptbl.md)

