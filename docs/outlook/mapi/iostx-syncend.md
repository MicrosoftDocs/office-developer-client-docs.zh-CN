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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 364914df1c5897241dfeb89cce2cc3c62018ce24
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332149"
---
# <a name="iostxsyncend"></a>IOSTX::SyncEnd

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在当前状态结束同步并退出该状态。
  
```cpp
HRESULT SyncEnd();
```

## <a name="remarks"></a>注解

客户端必须调用对[IOSTX:: SyncBeg](iostx-syncbeg.md)的每个调用的**IOSTX:: SyncEnd** 。 相应的数据结构包含用于指示客户端是否已成功完成当前状态的信息, 以便 Outlook 能够清除其内部状态。
  
## <a name="see-also"></a>另请参阅



[IOSTX::GetLastError](iostx-getlasterror.md)
  
[IOSTX::InitSync](iostx-initsync.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncBeg](iostx-syncbeg.md)
  
[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)
  
[IOSTX::SyncHdrEnd](iostx-synchdrend.md)
  
[IOSTX : IUnknown](iostxiunknown.md)


[MAPI 常量](mapi-constants.md)

