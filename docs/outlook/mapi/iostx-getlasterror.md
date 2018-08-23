---
title: IOSTXGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.GetLastError
api_type:
- COM
ms.assetid: b25c9288-b391-6303-3643-5a5b66b75c48
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 78ae0f78e154c17f774817238b2083d98a8fb809
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584679"
---
# <a name="iostxgetlasterror"></a>IOSTX::GetLastError

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
获取有关扩展的信息的最后一个错误。
  
```cpp
HRESULT GetLastError( 
    HRESULT hResult, 
    ULONG ulFlags, 
    LPMAPIERROR *lppMAPIError 
);
```

## <a name="parameters"></a>参数

 _hResult_
  
>  [in]错误代码。 
    
 _ulFlags_
  
>  [] in若要修改行为的标志。 这必须是 0。 
    
 _lppMAPIError_
  
>  [输出]指向包含错误的扩展的信息**MAPIERROR**结构。 请参阅 mapidefs.h **LPMAPIERROR**的类型定义。 
    
## <a name="see-also"></a>另请参阅



[IOSTX::InitSync](iostx-initsync.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncBeg](iostx-syncbeg.md)
  
[IOSTX::SyncEnd](iostx-syncend.md)
  
[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)
  
[IOSTX::SyncHdrEnd](iostx-synchdrend.md)
  
[IOSTX : IUnknown](iostxiunknown.md)


[MAPI 常量](mapi-constants.md)

