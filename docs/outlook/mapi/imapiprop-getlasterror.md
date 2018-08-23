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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f67dbb4d883f2f66099f2e2b9bc06b6c35b98236
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575831"
---
# <a name="imapipropgetlasterror"></a>IMAPIProp::GetLastError

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的错误的信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]在以前的方法调用中生成的错误代码句柄。
    
 _ulFlags_
  
> [in]位掩码的标志，指示返回所指的_lppMAPIError_ **MAPIERROR**结构中的文本的格式。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 字符串应为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，则字符串应以 ANSI 格式。
    
 _lppMAPIError_
  
> [输出]指向包含错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。 要返回的错误信息时， _lppMAPIError_参数可以设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 返回的错误的信息。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
## <a name="remarks"></a>注解

**IMAPIProp::GetLastError**方法提供有关失败的前一个方法调用的信息。 客户端可以其通过用户提供有关错误的详细信息对话框中包括的**MAPIERROR**结构中的数据。 
  
所有**GetLastError**供稿 MAPI 的实现都是 ANSI 实现，除[IAddrBook](iaddrbookimapiprop.md)实现。 附带**IAddrBook** **GetLastError**方法支持 Unicode。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

远程的详细信息传输提供程序的此方法的实现和什么此方法返回的消息是最多为传输提供程序，因为指向不同的 HRESULT 值的特定错误条件将不同的不同的传输提供程序。
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以使用如果**GetLastError**提供，仅当返回值是 S_OK _lppMAPIError_参数中，指向**MAPIERROR**结构。 有时**GetLastError**无法确定最后一个错误已或某种更多有关错误报告。 在这种情况下，为 NULL 的指针被返回在_lppMAPIError_中。 
  
释放**MAPIERROR**结构的内存，调用[MAPIFreeBuffer](mapifreebuffer.md)函数。 
  
有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)
  
[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MAPI 扩展错误](mapi-extended-errors.md)

