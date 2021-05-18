---
title: IOSTXSyncHdrBeg
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.SyncHdrBeg
api_type:
- COM
ms.assetid: 7f8ca7cf-ac0b-9b77-c1dd-9f1d0871d603
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 49ef9862d5156a1bed242652df32baab9a0123fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405091"
---
# <a name="iostxsynchdrbeg"></a>IOSTX::SyncHdrBeg

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启动邮件头的同步。
  
```cpp
HRESULT SyncHdrBeg( 
    ULONG cbeid, 
    LPENTRYID lpeid, 
    LPVOID *ppv 
);
```

## <a name="parameters"></a>参数

 _c一d_
  
> [in]邮件条目 ID 中的字节数。
    
 _lpeid_
  
> [in]邮件的条目 ID。
    
 _ppv_
  
>  [in]/[out] 指向 **[邮件头的 HDRSYNC](hdrsync.md)** 结构的指针。 
    
## <a name="remarks"></a>备注

在 **IOSTX：：SyncHdrBeg** 时，本地存储将转换为 [下载邮件头状态](download-message-header-state.md)。 Outlook使用存储和父文件夹中邮件头的当前表示形式初始化客户端 **的 HDRSYNC** 结构。 然后，客户端必须下载完整邮件项目 (**HDRSYNC** *中的 pmsgFull* ) 。 如果此操作成功，客户端还会将 **HDRSYNC** 中的 *ulFlags* **HSF_OK。** 在 **[IOSTX：：SyncHdrEnd](iostx-synchdrend.md)** Outlook **检查 HDRSYNC** 中的结果，并使用 **HDRSYNC** 中的信息更新本地邮件头。 
  
## <a name="see-also"></a>另请参阅



[IOSTX::GetLastError](iostx-getlasterror.md)
  
[IOSTX::InitSync](iostx-initsync.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncBeg](iostx-syncbeg.md)
  
[IOSTX::SyncEnd](iostx-syncend.md)
  
[IOSTX::SyncHdrEnd](iostx-synchdrend.md)
  
[IOSTX : IUnknown](iostxiunknown.md)


[MAPI 常量](mapi-constants.md)

