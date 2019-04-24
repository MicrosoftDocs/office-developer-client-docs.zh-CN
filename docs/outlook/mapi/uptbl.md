---
title: UPTBL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 39d9ad3b-ff4b-8378-a3ac-d5621c7ef7f1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b401f54df020fb6553cbdcc5b85206ee422a8429
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338855"
---
# <a name="uptbl"></a>UPTBL

**适用于**：Outlook 2013 | Outlook 2016 
  
[上载表状态](upload-table-state.md)期间上载文件夹内容的信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPTBL 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    LPSTR pszName; 
    FEID feid; 
    UINT uintReserved; 
    UPTBLE rgte[2]; 
    UINT iEnt; 
    UINT cEnt; 
    PUPMOV pupmovHead; 
    void* pReserved; 
};
```

## <a name="members"></a>成员

_ulFlags_
  
> 实时用于在上载过程中确定相应行为的标志。
    
  - UPT_OK
    
    - 实时上载成功。 客户端将文件夹内容上载到服务器后对此进行设置。
    
_pstmReserved_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_pszName_
  
> [传出] 文件夹的名称。
    
_feid_
  
> [传出] 文件夹的条目 ID。
    
_uintReserved_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_rgte_
  
> 排除用于保存文件夹中的普通 (或非隐藏) 项目以及关联 (或隐藏) 项目的以下信息的结构: _rgte [0]_ 适用于普通项目, 而_rgte [1]_ 用于关联的项目。 
    
   - 新项目或修改的项目的数量
   - 读取项目数 
   - 已删除项目的数量
    
 _iEnt_
  
> 排除用于跟踪上传由_分币_指定的更改数的索引。
    
_分币_
  
> 排除对文件夹所做的更改的数量。
    
_pupmovHead_
  
> 排除[UPMOV](upmov.md)结构的链。 
    
_保护_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [UPTBLE](uptble.md)

