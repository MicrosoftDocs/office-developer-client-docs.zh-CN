---
title: IProfAdminGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.GetLastError
api_type:
- COM
ms.assetid: bb161d7b-ae5b-4f8e-a506-8346ac5e583d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b6964ecde3a78bd1e9ce0ae1dcab0342c5a21a03
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317085"
---
# <a name="iprofadmingetlasterror"></a>IProfAdmin::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关配置文件管理对象中发生的上一个错误的信息。 
  
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
  
> 排除指向包含错误的版本、组件和上下文信息的**MAPIERROR**结构的指针的指针。 如果没有要返回的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
## <a name="remarks"></a>注解

**IProfAdmin:: GetLastError**方法检索有关从配置文件管理对象的方法调用中返回的最后一个错误的信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果 MAPI 提供了**MAPIERROR**结构, 则可以使用_lppMAPIError_参数仅在**GetLastError**返回 S_OK 时指向它。 有时 MAPI 无法确定最后一个错误是什么, 或者没有更多要报告错误的内容。 在这种情况下, 将在_lppMAPIError_中返回指向 NULL 的指针。 
  
若要释放 MAPI 为**MAPIERROR**结构分配的所有内存, 请调用[MAPIFreeBuffer](mapifreebuffer.md)函数。 
  
有关**GetLastError**方法的详细信息, 请参阅[使用扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)

