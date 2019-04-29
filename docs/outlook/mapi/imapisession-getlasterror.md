---
title: IMAPISessionGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.GetLastError
api_type:
- COM
ms.assetid: 38cb3692-a5f8-403a-9615-9bd5868af23c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7477213ee854be1ae71b47a0c1b339c4c13b6f04
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435577"
---
# <a name="imapisessiongetlasterror"></a>IMAPISession::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个会话错误的相关信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> 实时在上一方法调用中生成的错误值的句柄。
    
 _ulFlags_
  
> 实时用于控制返回的字符串类型的标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 在_lppMAPIError_参数中返回的**MAPIERROR**结构中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。 
    
 _lppMAPIError_
  
> 排除指向包含错误的版本、组件和上下文信息的**MAPIERROR**结构的指针的指针。 如果 MAPI 无法为**MAPIERROR**结构提供适当的信息, 则可以将_lppMAPIError_参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 已设置 MAPI_UNICODE 标志, 且会话不支持 UNICODE。
    
## <a name="remarks"></a>说明

**IMAPISession:: GetLastError**方法检索**IMAPISession**方法调用返回的上一个错误的相关信息。 通过在对话框中包含此信息, 客户端可以向其用户提供有关错误的详细信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果 MAPI 提供了**MAPIERROR**结构, 则可以使用_lppMAPIError_参数仅在**GetLastError**返回 S_OK 时指向它。 有时 MAPI 无法确定最后一个错误是什么, 或者它不会再报告有关错误的内容。 在这种情况下, **GetLastError**将返回指向_lppMAPIError_中的 NULL 的指针。 
  
有关**GetLastError**方法的详细信息, 请参阅[MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MAPI 扩展错误](mapi-extended-errors.md)

