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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 77688f8a09c1d990201a247a3c4e3a11ba0963b3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438622"
---
# <a name="imsprovidershutdown"></a>IMSProvider::Shutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
以有序的方式关闭邮件存储提供程序。
  
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
  
> 调用成功, 并返回了所需的一个或一些值。
    
## <a name="remarks"></a>说明

在释放邮件存储区提供程序对象之前, MAPI 会调用**IMSProvider:: Shutdown**方法。 MAPI 在为提供程序调用**Shutdown**之前释放该提供程序的所有登录对象。 
  
## <a name="see-also"></a>另请参阅



[IMSProvider : IUnknown](imsprovideriunknown.md)

