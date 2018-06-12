---
title: IOSTXInitSync
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.InitSync
api_type:
- COM
ms.assetid: e22244a2-ac5f-910a-501f-4483ea0667c2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 07305f712fd925b206ce18a32f8f5a24f199ccbf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775953"
---
# <a name="iostxinitsync"></a>IOSTX::InitSync

  
  
**适用于**： Outlook 
  
通知的本地消息存储同步即将开始。
  
```cpp
HRESULT InitSync( 
    ULONG ulFlags 
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]同步过程中确定适当的行为的标志。 Outlook 使用中的复制状态机每种状态这些标志来确定其应该为客户端提供的信息。 例如，如果客户端通过**SYNC_ONLY_ASSOCIATED**，Outlook 将仅返回与关联 （或隐藏） 的项相关的信息。 
    
## <a name="see-also"></a>另请参阅



[IOSTX::GetLastError](iostx-getlasterror.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncBeg](iostx-syncbeg.md)
  
[IOSTX::SyncEnd](iostx-syncend.md)
  
[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)
  
[IOSTX::SyncHdrEnd](iostx-synchdrend.md)
  
[IOSTX: IUnknown](iostxiunknown.md)


[MAPI 常量](mapi-constants.md)

