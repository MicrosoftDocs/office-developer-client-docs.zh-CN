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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409781"
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
  
> [In]保留;必须是指向零的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 连接已成功取消。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

在 Shutdown 方法 **的实现** 中，执行你认为必要的任何任务。 MAPI **仅在释放** 所有登录对象后调用 Shutdown 方法。 
  
## <a name="see-also"></a>另请参阅



[IABProvider : IUnknown](iabprovideriunknown.md)

