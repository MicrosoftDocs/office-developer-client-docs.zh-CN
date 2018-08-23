---
title: IMAPISyncProgressCallbackProgress
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISyncProgressCallback.Progress
api_type:
- COM
ms.assetid: 6797cd1c-8a0b-4f42-ba56-6162d8e7b058
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5803441486f01883d08cd99048d8eae133cd3f14
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592127"
---
# <a name="imapisyncprogresscallbackprogress"></a>IMAPISyncProgressCallback::Progress

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
更新发送/接收对话框中的状态。 存储提供程序定期调用此函数。
  
```cpp
HRESULT Progress(
  const WCHAR *pwcszProgress, 
  ULONG ulIndex, 
  ULONG ulIndexMax
);
```

## <a name="parameters"></a>参数

 **pwczsProgress**
  
> 一个指向一个字符串，显示当前进度步骤。 它可以为 NULL，以更新进度。
    
 **ulIndex**
  
> 正在进行中的当前位置。
    
 **ulIndexMax**
  
> 指示完成进度索引。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="see-also"></a>另请参阅



[IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md)

