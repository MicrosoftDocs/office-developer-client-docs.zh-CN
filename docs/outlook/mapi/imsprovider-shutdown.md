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
ms.openlocfilehash: 334ec8dd0c683cf9b765f387281c624b20520098
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775921"
---
# <a name="imsprovidershutdown"></a>IMSProvider::Shutdown

  
  
**适用于**： Outlook 
  
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
    
## <a name="remarks"></a>说明

MAPI 释放消息存储提供程序对象之前调用**IMSProvider::Shutdown**方法。 MAPI 的提供程序调用**关闭**之前释放提供程序的所有登录对象。 
  
## <a name="see-also"></a>另请参阅



[IMSProvider : IUnknown](imsprovideriunknown.md)

