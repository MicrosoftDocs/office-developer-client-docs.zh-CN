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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338862"
---
# <a name="upreade"></a>UPREADE

**适用于**：Outlook 2013 | Outlook 2016 
  
用于在[上载读取状态状态](upload-read-status-state.md)期间上载项目的读取状态的扩展信息。
  
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
  
>  [输出]/[in] 标志, 以确定在上载过程中的相应行为。 
    
  - UPR_ASSOC
    
    - 排除项目已隐藏。
    
  - UPR_READ
    
    - 排除项目的读取状态已更改。
    
  - UPR_OK
    
    - 实时上载成功。 客户端将信息上载到服务器后对此进行设置。
    
  - UPR_COMMIT
    
    - 实时立即上载项目的读取状态, 而不是等待[上载表状态](upload-table-state.md)的末尾, 以批处理的多个项目。 
    
_skey_
  
> 排除项的源键。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [UPREAD](upread.md)

