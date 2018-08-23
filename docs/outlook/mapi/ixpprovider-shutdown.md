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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2d9a58ff05bb0da07762b9eafddef7303e8b9bc5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592603"
---
# <a name="ixpprovidershutdown"></a>IXPProvider::Shutdown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
传输提供程序中有序的方式将关闭。
  
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
  
> 呼叫已成功关闭传输提供程序。
    
## <a name="remarks"></a>注解

MAPI 后台处理程序调用**IXPProvider::Shutdown**方法只之前释放传输提供程序对象。 调用之前**关闭**，MAPI 提供程序释放所有登录对象。
  
## <a name="see-also"></a>另请参阅



[XPProviderInit](xpproviderinit.md)
  
[IXPProvider : IUnknown](ixpprovideriunknown.md)

