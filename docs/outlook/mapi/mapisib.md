---
title: MAPISIB
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 16452798-7a95-43da-b95e-908debcea050
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cbda978a0d69367e95f9b4b1f53fd6d03b113ccc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270208"
---
# <a name="mapisib"></a>MAPISIB

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
此结构与[IMAPISync:: SynchronizeInBackground](imapisyncsynchronizeinbackground.md)一起使用。
  
```cpp
typedef struct _MAPISIB
{
ULONG           ulSize;                
ULONG           ulFlags;
LPMAPISESSION   psesSync;
LPUNKNOWN       punkCallBack;
HANDLE          *phSyncDoneEvent;    
} MAPISIB, *PMAPISIB
```

## <a name="members"></a>Members

 **ulSize**
  
> 结构的大小。
    
 **ulFlags**
  
> 指示同步类型的标志。它必须是下列值之一:
    
||||
|:-----|:-----|:-----|
|SYNC_OUTGOING_MAIL  <br/> |0x00000200  <br/> |将邮件发送到服务器 (当前未使用)。  <br/> |
|SYNC_UPLOAD_HIERARCHY  <br/> |0x00000001  <br/> |将层次结构更改推送到服务器。  <br/> |
|SYNC_DOWNLOAD_HIERARCHY  <br/> |0x00000002  <br/> |从服务器中拉取层次结构更改。  <br/> |
|SYNC_UPLOAD_CONTENTS  <br/> |0x00000040  <br/> |将邮件更改推送到服务器。  <br/> |
|SYNC_DOWNLOAD_CONTENTS  <br/> |0x00000080  <br/> |从服务器中提取邮件更改。  <br/> |
|SYNC_ON_DEMAND  <br/> |0x20000000  <br/> |同步是由用户启动的, 并且应具有更高的优先级。  <br/> |
|SYNC_GLOBAL_HEADERS  <br/> |0x02000000  <br/> |应仅同步标题, 而不应同步整个正文。  <br/> |
   
 **psesSync**
  
> 实时指向 MAPI 会话的指针。
    
 **punkCallBack**
  
> 实时指向在其上提供进度的接口的指针。 它可用于查询[IMAPISyncProgressCallback: IUnknown](imapisyncprogresscallbackiunknown.md)的接口。
    
 **\*phSyncDoneEvent**
  
> 排除在刚创建的线程完成时将发生的事件。 指针必须有效, 因为它将包含事件。
    
## <a name="see-also"></a>另请参阅



[IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md)
  
[IMAPISync : IUnknown](imapisynciunknown.md)

