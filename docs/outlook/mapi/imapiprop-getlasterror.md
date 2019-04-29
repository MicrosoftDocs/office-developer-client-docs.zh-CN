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
  
返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个错误的相关信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> 实时在上一方法调用中生成的错误代码的句柄。
    
 _ulFlags_
  
> 实时标志的位掩码, 指示由_lppMAPIError_指向的**MAPIERROR**结构中返回的文本的格式。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 字符串应采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串应为 ANSI 格式。
    
 _lppMAPIError_
  
> 排除指向包含错误的版本、组件和上下文信息的**MAPIERROR**结构的指针的指针。 如果没有要返回的错误消息, 则可以将_lppMAPIError_参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 返回错误消息。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
## <a name="remarks"></a>说明

**IMAPIProp:: GetLastError**方法提供有关失败的上一个方法调用的信息。 通过在对话框中包含**MAPIERROR**结构中的数据, 客户端可以向其用户提供有关错误的详细信息。 
  
除[IAddrBook](iaddrbookimapiprop.md)实现之外, MAPI 提供的所有**GetLastError**实现都是 ANSI 实现。 **IAddrBook**附带的**GetLastError**方法支持 Unicode。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

远程传输提供程序对此方法的实现以及此方法返回的消息的详细信息由传输提供程序使用, 因为导致不同的 HRESULT 值的特定错误条件将因不同传输而异商会.
  
## <a name="notes-to-callers"></a>给调用方的说明

如果**GetLastError**提供_lppMAPIError_参数所指向的**MAPIERROR**结构, 则只有当返回值为 S_OK 时, 才能使用它。 有时, **GetLastError**无法确定最后一个错误是什么, 或者没有更多要报告错误的内容。 在这种情况下, 将在_lppMAPIError_中返回指向 NULL 的指针。 
  
若要释放**MAPIERROR**结构的内存, 请调用[MAPIFreeBuffer](mapifreebuffer.md)函数。 
  
有关**GetLastError**方法的详细信息, 请参阅[MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)
  
[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MAPI 扩展错误](mapi-extended-errors.md)

