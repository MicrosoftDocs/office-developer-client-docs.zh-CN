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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317169"
---
# <a name="iostxsyncbeg"></a>IOSTX::SyncBeg

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
准备本地存储以在特定状态进行同步并检索要复制的必要信息。
  
```cpp
HRESULT SyncBeg( 
    UINT uiSync, 
    LPVOID *ppv 
);
```

## <a name="parameters"></a>参数

 _uiSync_
  
>  实时本地存储将输入的省/市/自治区。 以下是状态终止的列表: 
    
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
  
>  [in]/[out] 指针, 指向与要输入的状态相对应的数据结构。 
    
[DNHIER](dnhier.md)
  
> 
    
[DNTBL](dntbl.md)
  
> 
    
[DNTBL](dntbl.md)
  
> 
    
[同步](sync.md)
  
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
    
## <a name="remarks"></a>注解

客户端调用**[IOSTX:: SetSyncResult](iostx-setsyncresult.md)** 设置同步的结果, 然后调用**[IOSTX:: SyncEnd](iostx-syncend.md)** 结束该状态。 客户端必须为对**IOSTX:: SyncBeg**的每个调用调用**[IOSTX:: SyncEnd](iostx-syncend.md)** , 以确定状态是否已成功复制。 确定后, Outlook 可以开始清理其内部状态。 
  
大多数结构都包含 [out]/[in] 信息, 使 Outlook 能够将信息传递到客户端, 以及将信息传递给 Outlook 的客户端。 当客户端调用**IOSTX:: SyncBeg**时, Outlook 将为给定状态分配数据结构, 并使用该状态的信息对其进行初始化。 这是 [输出] 信息。 在状态下, 客户端更新该状态对应的数据结构。 这是 [!] 信息。 
  
## <a name="see-also"></a>另请参阅



[IOSTX::GetLastError](iostx-getlasterror.md)
  
[IOSTX::InitSync](iostx-initsync.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncEnd](iostx-syncend.md)
  
[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)
  
[IOSTX::SyncHdrEnd](iostx-synchdrend.md)
  
[IOSTX : IUnknown](iostxiunknown.md)


[MAPI 常量](mapi-constants.md)

