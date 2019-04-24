---
title: IABProviderShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABProvider.Shutdown
api_type:
- COM
ms.assetid: 1fbe6dc1-254b-4557-92c8-9fa42a8efd64
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8b2190f77c7575d3d4f5e25fa0863bec844158bc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348900"
---
# <a name="iabprovidershutdown"></a>IABProvider::Shutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
取消与活动会话的连接。
  
```cpp
HRESULT Shutdown(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> 实时保留必须是指向零的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功取消连接。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

在您的**Shutdown**方法实现中, 执行您认为必要的任何任务。 只有在发布了所有的登录对象之后, MAPI 才会调用您的**关闭**方法。 
  
## <a name="see-also"></a>另请参阅



[IABProvider : IUnknown](iabprovideriunknown.md)

