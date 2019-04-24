---
title: IMAPISessionEnumAdrTypes
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.EnumAdrTypes
api_type:
- COM
ms.assetid: 9a3702a4-8a6b-4c0c-a90f-02be3a2bfa05
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3b2e41c4b1bfc4879717df0c73bbcd45a724ca60
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338435"
---
# <a name="imapisessionenumadrtypes"></a>IMAPISession::EnumAdrTypes

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
已弃用。 返回会话中的所有传输提供程序可以处理的地址类型。 
  
```cpp
HRESULT EnumAdrTypes(
  ULONG ulFlags,
  ULONG FAR * lpcAdrTypes,
  LPSTR FAR * FAR * lpppszAdrTypes
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时标志的位掩码, 指示返回的地址类型的格式。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 地址类型为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则地址类型将采用 ANSI 格式。
    
 _lpcAdrTypes_
  
> 排除一个指针, 指向_lpppszAdrTypes_参数指向的地址类型的计数。 
    
 _lpppszAdrTypes_
  
> 排除指向指向地址类型的指针数组的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索地址类型。
    
## <a name="remarks"></a>注解

**IMAPISession:: EnumAdrTypes**方法返回会话中所有活动的传输提供程序可以处理的地址类型的列表。 当前未加载的传输提供程序的地址类型不包含在列表中。 当 MAPI 调用[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法时, 传输提供程序将注册以处理一个或多个地址类型。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用[MAPIFreeBuffer](mapifreebuffer.md)以释放_lpppszAdrTypes_参数指向的字符串数组。 
  
## <a name="see-also"></a>另请参阅



[IXPLogon::AddressTypes](ixplogon-addresstypes.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)

