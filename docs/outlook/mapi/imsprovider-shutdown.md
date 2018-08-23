---
title: IMSProviderShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSProvider.Shutdown
api_type:
- COM
ms.assetid: 9ca1861d-9bc9-485a-9807-a598b869e5a2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 342b87a3a8f0349631e64600e294d4f19ab1099c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589089"
---
# <a name="imsprovidershutdown"></a>IMSProvider::Shutdown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
关闭中有序的方式的消息存储提供程序。
  
```cpp
HRESULT Shutdown(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [in]保留;必须为零的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
## <a name="remarks"></a>注解

MAPI 释放消息存储提供程序对象之前调用**IMSProvider::Shutdown**方法。 MAPI 的提供程序调用**关闭**之前释放提供程序的所有登录对象。 
  
## <a name="see-also"></a>另请参阅



[IMSProvider : IUnknown](imsprovideriunknown.md)

