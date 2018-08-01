---
title: UPREADE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d146ee74-0c3a-5fdd-b1aa-af6498550801
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 854e674002953c31c47d56096700dca582ce0a5b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779065"
---
# <a name="upreade"></a>UPREADE

**适用于**： Outlook 
  
用于[上载读取状态状态](upload-read-status-state.md)期间上载读取项的状态的扩展的信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPREADE 
{ 
    ULONG ulFlags; 
    SKEY skey; 
};
```

## <a name="members"></a>Members

_ulFlags_
  
>  [out] / [输入] 要在上载过程中确定适当的行为的标志。 
    
  - UPR_ASSOC
    
    - [输出]项目处于隐藏状态。
    
  - UPR_READ
    
    - [输出]已更改项目的读取的状态。
    
  - UPR_OK
    
    - [in]上载成功。 客户端设置此后上载到服务器的信息。
    
  - UPR_COMMIT
    
    - [in]上载读取的项目的状态现在，而不是等待到末尾的[上载表状态](upload-table-state.md)批处理过程的多个项目。 
    
_skey_
  
> [输出]项目的源键。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态计算机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [UPREAD](upread.md)

