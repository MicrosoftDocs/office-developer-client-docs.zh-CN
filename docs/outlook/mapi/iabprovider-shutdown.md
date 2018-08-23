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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0a93dd44960a01996672a55501a7626d0ff56986
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567886"
---
# <a name="iabprovidershutdown"></a>IABProvider::Shutdown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
取消活动会话的连接。
  
```cpp
HRESULT Shutdown(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [In]保留;必须为零的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 连接成功已取消。
    
## <a name="notes-to-implementers"></a>针对实施者的注释

**Shutdown**方法的实现中, 执行考虑所需的任何任务。 只有在已发布您的所有登录对象后，MAPI 调用**Shutdown**方法。 
  
## <a name="see-also"></a>另请参阅



[IABProvider : IUnknown](iabprovideriunknown.md)

