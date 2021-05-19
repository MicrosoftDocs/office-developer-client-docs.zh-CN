---
title: UPREADE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d146ee74-0c3a-5fdd-b1aa-af6498550801
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1df2c665f8e9d7a0bd6d47ec59b2adf706bead75
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434142"
---
# <a name="upreade"></a>UPREADE

**适用于**：Outlook 2013 | Outlook 2016 
  
上传读取状态期间上传项目的读取 [状态的扩展信息](upload-read-status-state.md)。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPREADE 
{ 
    ULONG ulFlags; 
    SKEY skey; 
};
```

## <a name="members"></a>成员

_ulFlags_
  
>  [out]/[in] 用于确定上载期间的适当行为的标志。 
    
  - UPR_ASSOC
    
    - [out]项目处于隐藏状态。
    
  - UPR_READ
    
    - [out]项目的读取状态已更改。
    
  - UPR_OK
    
    - [in]Upload已成功。 客户端在将信息上载到服务器后进行设置。
    
  - UPR_COMMIT
    
    - [in]Upload项的读取状态，而不是等到上载表状态结束时再执行多个项目的批处理。 [](upload-table-state.md) 
    
_skey_
  
> [out]项的源键。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [UPREAD](upread.md)

