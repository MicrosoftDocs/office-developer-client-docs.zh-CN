---
title: UPDELE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c38aa8be-ae77-0c40-9843-42e07b80db6b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9bd61739b14d0ec382a9d582689c1049fe89429b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360541"
---
# <a name="updele"></a>UPDELE

**适用于**：Outlook 2013 | Outlook 2016 
  
已在本地存储区中删除的项目的扩展信息。 此信息在[上载删除状态状态](upload-delete-status-state.md)期间使用。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPDELE 
{ 
    ULONG ulFlags; 
    SKEY skey; 
    DWORD   dwReserved; 
    SBinary binChg; 
    SBinary binPcl; 
    SKEY skeyDst; 
    PUPMOV pupmov; 
};
```

## <a name="members"></a>成员

_ulFlags_
  
> [输出]/[in] 标志以确定上载过程中的相应行为。
    
  - UPD_ASSOC
    
    - 排除项目相关联。
    
  - UPD_MOV
    
    - 排除项目已移出。
    
  - UPD_OK 
    
    - 实时上载成功。 客户端将信息上载到服务器后对此进行设置。
    
  - UPD_MOVED
    
    - 实时已成功移动项目。
    
  - UPD_UPDATE
    
    - 实时将源项目标记为已修改。
    
  - UPD_COMMIT
    
    - 实时立即提交上载状态 (条目 0)。
    
_skey_
  
> 排除item 的源键。
    
_dwReserved_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。
    
_binChg_
  
> 排除如果项目已移动, 则更改目标项的键。
    
_binPcl_
  
> 排除如果项目已移动, 则更改目标项的列表。
    
_skeyDst_
  
> 排除如果项目已移动, 则为目标项的源键。
    
_pupmov_
  
> 排除目标文件夹信息 (如果项目已移动)。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md) 
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [SKEY](skey.md)
- [UPDEL](updel.md)
- [UPMOV](upmov.md)

