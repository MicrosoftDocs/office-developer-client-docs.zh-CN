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
description: 上次修改时间：2012 年 7 月 3 日
ms.openlocfilehash: 864c2d2dfd17c285b0d8a401d59ce5b7d0463864
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432770"
---
# <a name="iostxsynchdrend"></a>IOSTX::SyncHdrEnd

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
结束邮件头的同步。
  
```cpp
HRESULT SyncHdrEnd( 
    LPMAPIPROGRESS pprog 
);
```

## <a name="parameters"></a>参数

 _pprog_
  
> [in]用于同步移动或复制的消息的 **[IMAPIProgress](imapiprogressiunknown.md)** 接口。 有关 **LPMAPIPROGRESS** 的类型定义，请参阅 mapidefs.h。 
    
## <a name="remarks"></a>备注

在 **[IOSTX：：SyncBeg](iostx-syncbeg.md)** 时，本地存储将进入 [下载邮件头状态](download-message-header-state.md)。 客户端下载完整邮件项目 (**[HDRSYNC](hdrsync.md)** *中为 pmsgFull* ) 。 如果此操作成功，客户端还会将 **HDRSYNC** 中的 *ulFlags* **HSF_OK。** 当 **IOSTX：：SyncHdrEnd** 时，Outlook **在 HDRSYNC** 中检查结果，并使用 **HDRSYNC** 中的 *pprog* 和信息更新本地邮件头。 
  
本地存储将返回到上一 **[IOSTX：：SyncHdrBeg 之前的状态](iostx-synchdrbeg.md)**。 
  
## <a name="see-also"></a>另请参阅



[IOSTX::GetLastError](iostx-getlasterror.md)
  
[IOSTX::InitSync](iostx-initsync.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncBeg](iostx-syncbeg.md)
  
[IOSTX::SyncEnd](iostx-syncend.md)
  
[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)
  
[IOSTX : IUnknown](iostxiunknown.md)


[MAPI 常量](mapi-constants.md)

