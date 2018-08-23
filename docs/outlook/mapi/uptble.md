---
title: UPTBLE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f7fcb385-186d-d5fe-7104-fe0af09d5768
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b2523c149d98dacf9ad321a4a443382a39753fd5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592337"
---
# <a name="uptble"></a>UPTBLE

**适用于**： Outlook 2013 |Outlook 2016 
  
扩展的[上载表状态](upload-table-state.md)期间上载文件夹的内容的信息。
  
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

## <a name="members"></a>Members

 _iEntMod_
  
>  [输出]要跟踪上载新的或修改项的_cEntMod_数目的索引。 
    
 _cEntMod_
  
>  [输出]新的或修改的文件夹中的项目数。 
    
 _iEntRead_
  
>  [输出]索引来跟踪上载_cEntRead_读取的项目数。 
    
 _cEntRead_
  
>  [输出]读取的文件夹中的项目数。 
    
 _iEntDel_
  
>  [输出]删除项目的索引来跟踪上载_cEntDel_数。 
    
 _cEntDel_
  
>  [输出]已删除的文件夹中的项目数。 
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md) 
- [关于复制状态计算机](about-the-replication-state-machine.md)
- [UPTBL](uptbl.md)

