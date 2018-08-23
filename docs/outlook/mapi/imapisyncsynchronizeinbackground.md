---
title: IMAPISync SynchronizeInBackground
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISync.SynchronizeInBackground
api_type:
- COM
ms.assetid: c4aaca65-d553-476c-8c6d-5f880b6efdc1
description: 上次修改时间： 2012 年 6 月 26 日
ms.openlocfilehash: ee6fe07df894213331ab51f9abaa4008247dac07
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568775"
---
# <a name="imapisync--synchronizeinbackground"></a>IMAPISync : SynchronizeInBackground

 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 启动同步。 此方法是通过 Microsoft Outlook 2010 和 Microsoft Outlook 2013 调用，并由消息存储提供程序实现。 
  
```cpp
HRESULT SynchronizeInBackground (
  PMAPISIB psibpb
);
```

## <a name="parameters"></a>参数

 _psibpb_
  
> 通知的内容将同步的提供程序和访问提供可在同步过程中使用的接口。 它是[MAPISIB](mapisib.md)结构。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="see-also"></a>另请参阅



[IMAPISync : IUnknown](imapisynciunknown.md)
  
[MAPISIB](mapisib.md)

