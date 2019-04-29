---
title: IMAPISupportGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.GetLastError
api_type:
- COM
ms.assetid: 5b4290d9-230f-416a-9644-188578565c7b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c34c175c43ada03e982f08a27f675448ea24a567
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438545"
---
# <a name="imapisupportgetlasterror"></a>IMAPISupport::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个支持对象错误的相关信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> 实时对支持对象的上一个方法调用中生成的错误值的句柄。
    
 _ulFlags_
  
> 实时用于控制返回的字符串类型的标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 在_lppMAPIError_参数中返回的**MAPIERROR**结构中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。 
    
 _lppMAPIError_
  
> 排除指向包含错误的版本、组件和上下文信息的**MAPIERROR**结构的指针的指针。 如果无法提供具有相应错误消息的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志且 mapi 不支持 unicode, 或者未设置 MAPI_UNICODE, 且 mapi 仅支持 UNICODE。
    
## <a name="remarks"></a>说明

**IMAPISupport:: GetLastError**方法是为所有支持对象实现的。 通过在对话框中包含**MAPIERROR**结构中的数据, 呼叫者可以向其用户提供有关错误的详细信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

只有当**GetLastError**返回 S_OK 时, 才能在_lppMAPIError_参数中使用指向**MAPIERROR**结构的指针 (如果 MAPI 提供一个)。 有时 MAPI 无法确定是什么是最后一个错误, 或者它对错误报告没有更多的报告。 在这种情况下, _lppMAPIError_返回指向 NULL 的指针。 
  
有关**GetLastError**方法的详细信息, 请参阅[MAPI 扩展错误](mapi-extended-errors.md)。
  
若要释放 MAPI 分配的所有内存, 请调用返回的**MAPIERROR**结构的[MAPIFreeBuffer](mapifreebuffer.md)函数。 
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)


[MAPI 扩展错误](mapi-extended-errors.md)

