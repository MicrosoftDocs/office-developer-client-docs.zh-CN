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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 59b534a076aee6498be9146eabb69c62fca313ed
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775550"
---
# <a name="imapisessiongetlasterror"></a>IMAPISession::GetLastError

  
  
**适用于**： Outlook 
  
返回一个[MAPIERROR](mapierror.md)结构，其中包含有关以前会话错误的信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]在以前的方法调用中生成的错误值句柄。
    
 _ulFlags_
  
> [in]返回控制的字符串类型的标志位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 
    
 _lppMAPIError_
  
> [输出]指向包含错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。 _LppMAPIError_参数可以设置为 NULL，如果 MAPI 不能提供相应**MAPIERROR**结构的信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置该 MAPI_UNICODE 标记和会话不支持 Unicode。
    
## <a name="remarks"></a>说明

**IMAPISession::GetLastError**方法检索信息**IMAPISession**方法的调用返回的最后一个错误。 客户端可以向其用户提供有关错误的详细信息通过在对话框中包括此信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以使用**MAPIERROR**结构中，如果 MAPI 提供一个，由指向_lppMAPIError_参数才**GetLastError**返回 S_OK。 有时 MAPI 无法确定最后一个错误是什么，或者它具有更多有关错误报告 nothing。 在此情况下， **GetLastError**返回一个指针为 NULL 中_lppMAPIError_相反。 
  
有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MAPI 扩展错误](mapi-extended-errors.md)

