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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6bd13eb7180302a5ab770586cf36856ca5a22676
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775548"
---
# <a name="imapisessionenumadrtypes"></a>IMAPISession::EnumAdrTypes

  
  
**适用于**： Outlook 
  
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
  
> [in]位掩码的标志，指示返回的地址类型的格式。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 地址类型的 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，地址类型的 ANSI 格式。
    
 _lpcAdrTypes_
  
> [输出]一个指向_lpppszAdrTypes_参数指向的地址类型的计数。 
    
 _lpppszAdrTypes_
  
> [输出]指向数组的指向地址类型的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索地址类型。
    
## <a name="remarks"></a>说明

**IMAPISession::EnumAdrTypes**方法返回会话中的所有活动传输提供程序可以处理的地址类型列表。 当前未加载的传输提供程序的地址类型不包含在该列表中。 传输提供程序注册，以处理时 MAPI 调用其[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法的一个或多个地址类型。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用[MAPIFreeBuffer](mapifreebuffer.md)释放_lpppszAdrTypes_参数指向的字符串数组。 
  
## <a name="see-also"></a>另请参阅



[IXPLogon::AddressTypes](ixplogon-addresstypes.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)

