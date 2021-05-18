---
title: IOSTXSyncBeg
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.SyncBeg
api_type:
- COM
ms.assetid: 4a935df3-98c4-2742-206e-4e16eda7b9bc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ae4497295328155780fc5208d1699169698e02d8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411937"
---
# <a name="iostxsyncbeg"></a>IOSTX::SyncBeg

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
准备本地存储以用于特定状态同步，并检索要复制的必要信息。
  
```cpp
HRESULT SyncBeg( 
    UINT uiSync, 
    LPVOID *ppv 
);
```

## <a name="parameters"></a>参数

 _uiSync_
  
>  [in]本地存储将进入的状态。 以下是状态标识列表： 
    
LR_SYNC_IDLE
  
> 
    
LR_SYNC
  
> 
    
LR_SYNC_UPLOAD_HIERARCHY
  
> 
    
LR_SYNC_UPLOAD_FOLDER
  
> 
    
LR_SYNC_CONTENTS
  
> 
    
LR_SYNC_UPLOAD_TABLE
  
> 
    
LR_SYNC_UPLOAD_MESSAGE
  
> 
    
LR_SYNC_UPLOAD_MESSAGE_READ
  
> 
    
LR_SYNC_UPLOAD_MESSAGE_DEL
  
> 
    
LR_SYNC_DOWNLOAD_HIERARCHY
  
> 
    
LR_SYNC_DOWNLOAD_TABLE
  
> 
    
 _ppv_
  
>  [in]/[out] 指向对应于要输入的状态的数据结构的指针。 
    
[DNHIER](dnhier.md)
  
> 
    
[DNTBL](dntbl.md)
  
> 
    
[DNTBL](dntbl.md)
  
> 
    
[SYNC](sync.md)
  
> 
    
[SYNCCONT](synccont.md)
  
> 
    
[UPDEL](updel.md)
  
> 
    
[UPDELE](updele.md)
  
> 
    
[UPFLD](upfld.md)
  
> 
    
[UPHIER](uphier.md)
  
> 
    
[UPMOV](upmov.md)
  
> 
    
[UPMSG](upmsg.md)
  
> 
    
[UPREAD](upread.md)
  
> 
    
[UPREADE](upreade.md)
  
> 
    
[UPTBL](uptbl.md)
  
> 
    
[UPTBLE](uptble.md)
  
> 
    
## <a name="remarks"></a>备注

客户端调用 **[IOSTX：：SetSyncResult](iostx-setsyncresult.md)** 以设置同步结果，然后调用 **[IOSTX：：SyncEnd](iostx-syncend.md)** 结束该状态。 对于每次调用 **IOSTX：：SyncBeg** 时，客户端必须调用 **[IOSTX：：SyncEnd，](iostx-syncend.md)** 以确定是否已成功复制状态。 确定此状态后，Outlook可以开始清理其内部状态。 
  
其中大多数结构包含 [out]/[in] 信息，Outlook向客户端传递信息，客户端将信息传递到Outlook。 当客户端调用 **IOSTX：：SyncBeg** 时，Outlook为给定状态分配数据结构，并初始化该状态的信息。 这是 [out] 信息。 当状态为 时，客户端会更新相应状态对应的数据结构。 这是 [in] 信息。 
  
## <a name="see-also"></a>另请参阅



[IOSTX::GetLastError](iostx-getlasterror.md)
  
[IOSTX::InitSync](iostx-initsync.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncEnd](iostx-syncend.md)
  
[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)
  
[IOSTX::SyncHdrEnd](iostx-synchdrend.md)
  
[IOSTX : IUnknown](iostxiunknown.md)


[MAPI 常量](mapi-constants.md)

