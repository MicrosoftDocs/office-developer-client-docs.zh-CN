---
title: IXPProviderShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPProvider.Shutdown
api_type:
- COM
ms.assetid: e2d8a025-c2a3-4edb-b6e4-022e07e854dd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a57a72b413ba412154a27a08244e86b117cbea7d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409690"
---
# <a name="ixpprovidershutdown"></a>IXPProvider::Shutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
以有序方式关闭传输提供程序。
  
```cpp
HRESULT Shutdown (
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功关闭传输提供程序。
    
## <a name="remarks"></a>备注

MAPI 后台处理程序在释放传输提供程序对象之前调用 **IXPProvider：：Shutdown** 方法。 在调用 **Shutdown** 之前，MAPI 会释放提供程序的所有登录对象。
  
## <a name="see-also"></a>另请参阅



[XPProviderInit](xpproviderinit.md)
  
[IXPProvider : IUnknown](ixpprovideriunknown.md)

