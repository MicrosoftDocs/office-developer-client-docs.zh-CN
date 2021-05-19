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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424880"
---
# <a name="updele"></a>UPDELE

**适用于**：Outlook 2013 | Outlook 2016 
  
已在本地存储中删除的项目的扩展信息。 此信息在上载删除 [状态期间使用](upload-delete-status-state.md)。
  
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
  
> [out]/[in] 用于确定上传期间适当行为的标志。
    
  - UPD_ASSOC
    
    - [out]项目已关联。
    
  - UPD_MOV
    
    - [out]项目已移出。
    
  - UPD_OK 
    
    - [in]Upload已成功。 客户端在将信息上载到服务器后进行设置。
    
  - UPD_MOVED
    
    - [in]项目已成功移动。
    
  - UPD_UPDATE
    
    - [in]将源项目标记为已修改。
    
  - UPD_COMMIT
    
    - [in]提交上传状态 (项 0) 。
    
_skey_
  
> [out]项的源键。
    
_dwReserved_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。
    
_binChg_
  
> [out]更改目标项的键（如果项目已移动）。
    
_binPcl_
  
> [out]更改目标项列表（如果项目已移动）。
    
_skeyDst_
  
> [out]目标项的源键（如果项目已移动）。
    
_pupmov_
  
> [out]目标文件夹信息（如果项目已移动）。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md) 
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [SKEY](skey.md)
- [UPDEL](updel.md)
- [UPMOV](upmov.md)

