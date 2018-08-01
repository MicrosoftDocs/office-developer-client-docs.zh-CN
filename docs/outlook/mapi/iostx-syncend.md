---
title: IOSTXSyncEnd
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.SyncEnd
api_type:
- COM
ms.assetid: da9de705-bdab-6cb8-35ea-61f03cdc4ff5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 66542d2cc7600ecbcd8de9043b6b40559744c2ad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775964"
---
# <a name="iostxsyncend"></a>IOSTX::SyncEnd

  
  
**适用于**： Outlook 
  
结束同步中的当前状态并退出该状态。
  
```cpp
HRESULT SyncEnd();
```

## <a name="remarks"></a>说明

客户端必须[IOSTX::SyncBeg](iostx-syncbeg.md)到每个呼叫的呼叫**IOSTX::SyncEnd** 。 相应的数据结构包含信息，以指示是否以便其内部状态可以清除，Outlook，客户端已成功完成的当前状态。
  
## <a name="see-also"></a>另请参阅



[IOSTX::GetLastError](iostx-getlasterror.md)
  
[IOSTX::InitSync](iostx-initsync.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncBeg](iostx-syncbeg.md)
  
[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)
  
[IOSTX::SyncHdrEnd](iostx-synchdrend.md)
  
[IOSTX : IUnknown](iostxiunknown.md)


[MAPI 常量](mapi-constants.md)

