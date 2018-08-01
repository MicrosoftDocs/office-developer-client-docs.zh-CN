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
ms.openlocfilehash: a8044eb6647e6f437c87bb4d8b021c62ea15f606
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776393"
---
# <a name="mapisib"></a>MAPISIB

  
  
**适用于**： Outlook 
  
此结构用于[IMAPISync::SynchronizeInBackground](imapisyncsynchronizeinbackground.md)。
  
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
  
> 指示的同步类型的标志。它必须是下列值之一：
    
||||
|:-----|:-----|:-----|
|SYNC_OUTGOING_MAIL  <br/> |0x00000200  <br/> |向服务器 （当前未在使用） 发送消息。  <br/> |
|SYNC_UPLOAD_HIERARCHY  <br/> |0x00000001  <br/> |层次结构更改推送到服务器。  <br/> |
|SYNC_DOWNLOAD_HIERARCHY  <br/> |0x00000002  <br/> |从服务器中提取层次结构更改。  <br/> |
|SYNC_UPLOAD_CONTENTS  <br/> |0x00000040  <br/> |消息更改推送到服务器。  <br/> |
|SYNC_DOWNLOAD_CONTENTS  <br/> |0x00000080  <br/> |从服务器中提取消息更改。  <br/> |
|SYNC_ON_DEMAND  <br/> |0x20000000  <br/> |同步用户启动，并且应更高的优先级。  <br/> |
|SYNC_GLOBAL_HEADERS  <br/> |0x02000000  <br/> |应仅同步邮件头和不完整的正文。  <br/> |
   
 **psesSync**
  
> [输入]一个指向 MAPI 会话。
    
 **punkCallBack**
  
> [输入]指向要提供进度接口的指针。 可用于查询的界面[IMAPISyncProgressCallback: IUnknown](imapisyncprogresscallbackiunknown.md)。
    
 **\*phSyncDoneEvent**
  
> [输出]刚刚创建的线程完成时，则会发生该事件。 指针必须是有效，因为它会包含该事件。
    
## <a name="see-also"></a>另请参阅



[IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md)
  
[IMAPISync : IUnknown](imapisynciunknown.md)

