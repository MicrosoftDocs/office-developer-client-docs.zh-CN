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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b9086383b45d40d5839284ac785d72438be60e00
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413351"
---
# <a name="iostxinitsync"></a>IOSTX::InitSync

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通知本地邮件存储即将开始同步。
  
```cpp
HRESULT InitSync( 
    ULONG ulFlags 
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]用于确定同步期间的适当行为的标志。 Outlook在复制状态机的每个状态中使用这些标志来确定应为客户端提供的信息。 例如，如果客户端向 SYNC_ONLY_ASSOCIATED **，Outlook** 将仅返回与项目关联的 (或) 的信息。 
    
## <a name="see-also"></a>另请参阅



[IOSTX::GetLastError](iostx-getlasterror.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncBeg](iostx-syncbeg.md)
  
[IOSTX::SyncEnd](iostx-syncend.md)
  
[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)
  
[IOSTX::SyncHdrEnd](iostx-synchdrend.md)
  
[IOSTX : IUnknown](iostxiunknown.md)


[MAPI 常量](mapi-constants.md)

