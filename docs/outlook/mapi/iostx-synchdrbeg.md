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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317155"
---
# <a name="iostxsynchdrbeg"></a>IOSTX::SyncHdrBeg

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启动邮件头同步。
  
```cpp
HRESULT SyncHdrBeg( 
    ULONG cbeid, 
    LPENTRYID lpeid, 
    LPVOID *ppv 
);
```

## <a name="parameters"></a>参数

 _cbeid_
  
> 实时邮件的条目 ID 中的字节数。
    
 _lpeid_
  
> 实时邮件的条目 ID。
    
 _ppv_
  
>  [in]/[out] 指针, 指向邮件头的**[HDRSYNC](hdrsync.md)** 结构。 
    
## <a name="remarks"></a>注解

在**IOSTX:: SyncHdrBeg**中, 本地存储将转换为[下载邮件头状态](download-message-header-state.md)。 Outlook 为客户端初始化存储和父文件夹中的邮件头的当前表示形式的**HDRSYNC**结构。 然后, 客户端必须下载完整的邮件项目 (在**HDRSYNC**中为*pmsgFull* )。 如果成功, 客户端还会将**HDRSYNC**中的*ulFlags*设置为**HSF_OK**。 在**[IOSTX:: SyncHdrEnd](iostx-synchdrend.md)** 上, Outlook 检查**HDRSYNC**中的结果, 并使用**HDRSYNC**中的信息更新本地邮件头。 
  
## <a name="see-also"></a>另请参阅



[IOSTX::GetLastError](iostx-getlasterror.md)
  
[IOSTX::InitSync](iostx-initsync.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncBeg](iostx-syncbeg.md)
  
[IOSTX::SyncEnd](iostx-syncend.md)
  
[IOSTX::SyncHdrEnd](iostx-synchdrend.md)
  
[IOSTX : IUnknown](iostxiunknown.md)


[MAPI 常量](mapi-constants.md)

