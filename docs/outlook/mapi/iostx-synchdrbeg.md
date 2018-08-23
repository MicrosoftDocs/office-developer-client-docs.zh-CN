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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2d05592d1fdcdcd53c8b7879f9cdcd432df1a3f7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579464"
---
# <a name="iostxsynchdrbeg"></a>IOSTX::SyncHdrBeg

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
邮件头的启动同步。
  
```cpp
HRESULT SyncHdrBeg( 
    ULONG cbeid, 
    LPENTRYID lpeid, 
    LPVOID *ppv 
);
```

## <a name="parameters"></a>参数

 _cbeid_
  
> [in]中的邮件的条目 ID 的字节数。
    
 _lpeid_
  
> [in]消息的条目 ID。
    
 _ppv_
  
>  [in] / [输出] 指向邮件头的**[HDRSYNC](hdrsync.md)** 结构。 
    
## <a name="remarks"></a>注解

时**IOSTX::SyncHdrBeg**，本地存储过渡到[下载邮件头状态](download-message-header-state.md)。 Outlook 客户端初始化**HDRSYNC**结构中的存储，并且父文件夹的邮件头的当前表示。 客户端必须然后下载完整邮件项目 （在**HDRSYNC** *pmsgFull* )。 如果这是成功，客户端还*ulFlags*中设置**HDRSYNC** **HSF_OK**。 时**[IOSTX::SyncHdrEnd](iostx-synchdrend.md)**，Outlook 检查**HDRSYNC**结果，并使用**HDRSYNC**中的信息来更新本地邮件头。 
  
## <a name="see-also"></a>另请参阅



[IOSTX::GetLastError](iostx-getlasterror.md)
  
[IOSTX::InitSync](iostx-initsync.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncBeg](iostx-syncbeg.md)
  
[IOSTX::SyncEnd](iostx-syncend.md)
  
[IOSTX::SyncHdrEnd](iostx-synchdrend.md)
  
[IOSTX : IUnknown](iostxiunknown.md)


[MAPI 常量](mapi-constants.md)

