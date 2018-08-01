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
ms.openlocfilehash: 2f1872c6f95f8ab12014de9890b0d03789bc5f0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775236"
---
# <a name="iabprovidershutdown"></a>IABProvider::Shutdown

  
  
**适用于**： Outlook 
  
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

