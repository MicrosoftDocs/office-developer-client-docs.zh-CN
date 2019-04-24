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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357195"
---
# <a name="ixpprovidershutdown"></a>IXPProvider::Shutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
以有序的方式关闭传输提供程序。
  
```cpp
HRESULT Shutdown (
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> 实时保留必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功关闭了传输提供程序。
    
## <a name="remarks"></a>注解

MAPI 后台处理程序在释放传输提供程序对象之前, 先调用**IXPProvider:: Shutdown**方法。 在呼叫**关闭**之前, MAPI 将释放所有登录对象的提供程序。
  
## <a name="see-also"></a>另请参阅



[XPProviderInit](xpproviderinit.md)
  
[IXPProvider : IUnknown](ixpprovideriunknown.md)

