---
title: IMAPIPropGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.GetLastError
api_type:
- COM
ms.assetid: f64a765d-c653-4eef-a0fc-24a54968757c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8c31cbf0472d3d64c7327fcfc80480ef27a1638e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435829"
---
# <a name="imapipropgetlasterror"></a>IMAPIProp::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个错误的信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]上一个方法调用中生成的错误代码的句柄。
    
 _ulFlags_
  
> [in]指示由 _lppMAPIError_ 指向 **的 MAPIERROR** 结构中返回的文本的格式的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 字符串应为 Unicode 格式。 如果未MAPI_UNICODE，则字符串应为 ANSI 格式。
    
 _lppMAPIError_
  
> [out]指向指向 **MAPIERROR** 结构的指针的指针，该结构包含错误的版本、组件和上下文信息。 如果没有  _要返回的错误信息，可以将 lppMAPIError_ 参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 返回了错误信息。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
## <a name="remarks"></a>备注

**IMAPIProp：：GetLastError** 方法提供有关失败之前的方法调用的信息。 客户端可以通过在对话框中包含 **MAPIERROR** 结构的数据，为用户提供有关错误的详细信息。 
  
MAPI 提供的所有 **GetLastError** 实现都是 ANSI 实现 [，IAddrBook](iaddrbookimapiprop.md) 实现除外。 **IAddrBook** 中包含的 **GetLastError** 方法支持 Unicode。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

远程传输提供程序实现此方法的详细信息以及此方法返回的邮件由传输提供程序决定，因为导致各种 HRESULT 值的特定错误条件对于不同的传输提供程序是不同的。
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以使用 _lppMAPIError_ 参数指向的 **MAPIERROR** 结构，如果 **GetLastError** 提供了一个，则仅在返回值为 S_OK。 有时 **，GetLastError** 无法确定上一个错误是什么，或者没有更多关于错误的报告。 在这种情况下，将改为在  _lppMAPIError_ 中返回指向 NULL 的指针。 
  
若要释放 **MAPIERROR** 结构的内存，请调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数。 
  
有关 **GetLastError** 方法的详细信息，请参阅 [MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)
  
[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MAPI 扩展错误](mapi-extended-errors.md)

