---
title: IMAPISyncProgressCallbackError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISyncProgressCallback.Error
api_type:
- COM
ms.assetid: 4860992d-65d7-4cb0-a874-ceccb153dbac
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8cff424e3b589af292e56cef1ca19198e9c80d1f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594983"
---
# <a name="imapisyncprogresscallbackerror"></a>IMAPISyncProgressCallback::Error

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供发送/接收对话框中显示的详细信息。 如果同步过程中遇到错误，存储提供程序调用此函数。
  
```cpp
HRESULT Error(
  HRESULT hResult,
  const WCHAR *pwcszErrorStr
);
```

## <a name="parameters"></a>参数

 **hResult**
  
> 相应的 HRESULT 错误或警告。
    
 **pwcszErrorStr**
  
> 指向与该错误以显示关联的字符串的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="see-also"></a>另请参阅



[IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md)

