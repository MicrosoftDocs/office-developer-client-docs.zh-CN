---
title: IProviderAdminGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProviderAdmin.GetLastError
api_type:
- COM
ms.assetid: 853ddee5-24d6-423d-b483-6a07a12de51f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4fc4867d5ca20f8e770afa239b0dffbd8ab1c480
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439847"
---
# <a name="iprovideradmingetlasterror"></a>IProviderAdmin::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关提供程序管理对象发生的上一个错误的信息。 
  
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
  
> 在_lppMAPIError_参数中返回的**MAPIERROR**中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。 
    
 _lppMAPIError_
  
> 排除指向包含错误的版本、组件和上下文信息的返回的**MAPIERROR**结构的指针的指针。 如果没有要返回的**MAPIERROR** , 则可以将_lppMAPIError_参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且**getlasterror**不支持 unicode, 或者未设置 MAPI_UNICODE, 且**GetLastError**仅支持 UNICODE。 
    
## <a name="remarks"></a>说明

**IProviderAdmin:: GetLastError**方法提供有关失败的上一个方法调用的信息。 通过在对话框中包含**MAPIERROR**结构中的数据, 呼叫者可以向其用户提供有关错误的详细信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以使用**MAPIERROR**结构 (如果 MAPI 提供一个), _lppMAPIError_参数仅在**GetLastError**返回 S_OK 时指向。 有时 MAPI 无法确定最后一个错误是什么, 或者没有更多要报告错误的内容。 在这种情况下, 将在_lppMAPIError_中返回指向 NULL 的指针。 
  
有关**GetLastError**方法的详细信息, 请参阅[使用扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IProviderAdmin : IUnknown](iprovideradminiunknown.md)

