---
title: IPersistMessageGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.GetLastError
api_type:
- COM
ms.assetid: 32cc3a1f-1310-4788-b0f4-93c1e4940f37
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2189a39e115236e6c2ec9de8a263ce3982d8b8e0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317162"
---
# <a name="ipersistmessagegetlasterror"></a>IPersistMessage::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关 form 对象中的前一个错误的信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> 实时一个 HRESULT 数据类型, 其中包含在上一方法调用中生成的错误值。
    
 _ulFlags_
  
> 实时用于控制返回的字符串类型的标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 在_lppMAPIError_参数中返回的[MAPIERROR](mapierror.md)结构中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。 
    
 _lppMAPIError_
  
> 排除指向包含错误的版本、组件和上下文信息的**MAPIERROR**结构的指针的指针。 如果窗体无法为**MAPIERROR**结构提供适当的信息, 则可以将_lppMAPIError_参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且通讯簿提供程序不支持 unicode, 或者未设置 MAPI_UNICODE, 并且通讯簿提供程序仅支持 unicode。
    
## <a name="remarks"></a>注解

Form 对象实现**IPersistMessage:: GetLastError**方法, 以提供有关失败的上一个方法调用的信息。 通过在对话框中包含[MAPIERROR](mapierror.md)结构中的数据, 表单查看者可以向其用户提供有关错误的详细信息。 
  
对**GetLastError**的调用不会影响窗体的状态。 当返回**GetLastError**时, 窗体将保持在进行调用之前的状态。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果窗体提供了**MAPIERROR**结构, 则只有当**GetLastError**返回 S_OK 时, 才能使用_lppMAPIError_参数所指向的结构。 有时, 窗体无法确定最后一个错误是什么, 或者对错误报告没有更多的信息。 在这种情况下, 表单将在_lppMAPIError_中返回指向 NULL 的指针。 
  
有关**GetLastError**方法的详细信息, 请参阅[MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IPersistMessage : IUnknown](ipersistmessageiunknown.md)

