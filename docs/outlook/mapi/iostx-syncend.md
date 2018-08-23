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
ms.openlocfilehash: fd5b2ed23eba30cbe861a20c4fd100cb8ea1aeb0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568838"
---
# <a name="iostxsyncend"></a>IOSTX::SyncEnd

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
结束同步中的当前状态并退出该状态。
  
```cpp
HRESULT SyncEnd();
```

## <a name="remarks"></a>注解

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

