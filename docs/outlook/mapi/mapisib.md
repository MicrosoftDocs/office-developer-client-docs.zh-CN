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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418706"
---
# <a name="mapisib"></a>MAPISIB

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
此结构与 [IMAPISync：：SynchronizeInBackground 一起使用](imapisyncsynchronizeinbackground.md)。
  
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
  
> 指示同步类型的标志。它必须是下列值之一：
    
||||
|:-----|:-----|:-----|
|SYNC_OUTGOING_MAIL  <br/> |0x00000200  <br/> |将邮件发送到当前 (使用的服务器) 。  <br/> |
|SYNC_UPLOAD_HIERARCHY  <br/> |0x00000001  <br/> |将层次结构更改推送到服务器。  <br/> |
|SYNC_DOWNLOAD_HIERARCHY  <br/> |0x00000002  <br/> |从服务器拉取层次结构更改。  <br/> |
|SYNC_UPLOAD_CONTENTS  <br/> |0x00000040  <br/> |将邮件更改推送到服务器。  <br/> |
|SYNC_DOWNLOAD_CONTENTS  <br/> |0x00000080  <br/> |从服务器拉取邮件更改。  <br/> |
|SYNC_ON_DEMAND  <br/> |0x20000000  <br/> |同步由用户启动，并且应具有更高的优先级。  <br/> |
|SYNC_GLOBAL_HEADERS  <br/> |0x02000000  <br/> |应仅同步标头，而不是完全正文。  <br/> |
   
 **psesSync**
  
> [IN]指向 MAPI 会话的指针。
    
 **punkCallBack**
  
> [IN]指向要提供进度的接口的指针。 它可用于查询 [IMAPISyncProgressCallback ： IUnknown 的接口](imapisyncprogresscallbackiunknown.md)。
    
 **\*phSyncDoneEvent**
  
> [OUT]刚刚创建的线程完成时将发生的事件。 指针必须有效，因为它将包含 事件。
    
## <a name="see-also"></a>另请参阅



[IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md)
  
[IMAPISync : IUnknown](imapisynciunknown.md)

