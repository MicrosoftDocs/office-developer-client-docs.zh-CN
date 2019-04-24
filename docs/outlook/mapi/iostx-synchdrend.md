---
title: IOSTXSyncHdrEnd
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.SyncHdrEnd
api_type:
- COM
ms.assetid: a0beb6eb-7978-c64e-dba1-89f0caf2090e
description: 上次修改时间:03 月3日, 2012
ms.openlocfilehash: 864c2d2dfd17c285b0d8a401d59ce5b7d0463864
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332184"
---
# <a name="iostxsynchdrend"></a>IOSTX::SyncHdrEnd

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
结束邮件头同步。
  
```cpp
HRESULT SyncHdrEnd( 
    LPMAPIPROGRESS pprog 
);
```

## <a name="parameters"></a>参数

 _pprog_
  
> 实时用于同步已移动或已复制邮件的**[IMAPIProgress](imapiprogressiunknown.md)** 接口。 有关**LPMAPIPROGRESS**的类型定义, 请参阅 mapidefs.h。 
    
## <a name="remarks"></a>注解

在**[IOSTX:: SyncBeg](iostx-syncbeg.md)** 中, 本地存储将进入[下载邮件头状态](download-message-header-state.md)。 客户端下载完整的邮件项目 (在**[HDRSYNC](hdrsync.md)** 中为*pmsgFull* )。 如果成功, 客户端还会将**HDRSYNC**中的*ulFlags*设置为**HSF_OK**。 在**IOSTX:: SyncHdrEnd**中, Outlook 检查**HDRSYNC**中的结果, 并使用*pprog*和**HDRSYNC**中的信息更新本地邮件头。 
  
本地存储将返回到它在前面的**[IOSTX:: SyncHdrBeg](iostx-synchdrbeg.md)** 之前的状态。 
  
## <a name="see-also"></a>另请参阅



[IOSTX::GetLastError](iostx-getlasterror.md)
  
[IOSTX::InitSync](iostx-initsync.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncBeg](iostx-syncbeg.md)
  
[IOSTX::SyncEnd](iostx-syncend.md)
  
[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)
  
[IOSTX : IUnknown](iostxiunknown.md)


[MAPI 常量](mapi-constants.md)

