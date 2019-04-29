---
title: IMSLogonGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.GetLastError
api_type:
- COM
ms.assetid: 3e296f6d-4833-4c68-9b84-df0b09878474
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 472502d0f033370b06a69596944350152ab794f9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425874"
---
# <a name="imslogongetlasterror"></a>IMSLogon::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关邮件存储对象的最后一个错误的信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> 实时一个 HRESULT 数据类型, 其中包含在以前的方法调用中为邮件存储对象生成的错误值。
    
 _ulFlags_
  
> 实时用于控制返回的字符串类型的标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 在_lppMAPIError_参数中返回的**MAPIERROR**结构中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。 
    
 _lppMAPIError_
  
> 排除指向包含错误的版本、组件和上下文信息的返回的**MAPIERROR**结构的指针的指针。 如果没有要返回的**MAPIERROR** , 则可以将_lppMAPIError_参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
## <a name="remarks"></a>说明

使用**IMSLogon:: GetLastError**方法检索信息, 以供用户显示在邮件中, 以便与邮件存储对象的方法调用中返回的最后一个错误有关。 
  
若要释放 MAPI 为返回的**MAPIERROR**结构分配的所有内存, 客户端应用程序只需调用[MAPIFreeBuffer](mapifreebuffer.md)函数。 
  
对于要使用**MAPIERROR**的应用程序, 从**GetLastError**返回的值必须为 S_OK。 即使返回值为 S_OK, 也可能不会返回**MAPIERROR** 。 如果实现无法确定上一个错误是什么, 或者**MAPIERROR**不能用于该错误, 则**GetLastError**将返回指向_lppMAPIError_中的 NULL 的指针而不是。 
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

