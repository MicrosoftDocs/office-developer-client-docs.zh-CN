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
  
返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个会话错误的信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]上一个方法调用中生成的错误值的句柄。
    
 _ulFlags_
  
> [in]控制返回的字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> _lppMAPIError_ 参数中返回的 **MAPIERROR** 结构中的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。 
    
 _lppMAPIError_
  
> [out]指向 **MAPIERROR** 结构的指针的指针，其中包含错误的版本、组件和上下文信息。 如果 MAPI 无法为 **MAPIERROR** 结构提供适当的信息，可以将 _lppMAPIError_ 参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 已MAPI_UNICODE该标记，并且会话不支持 Unicode。
    
## <a name="remarks"></a>备注

**IMAPISession：：GetLastError** 方法检索 **有关 IMAPISession** 方法调用返回的最后一个错误的信息。 客户端可以通过在对话框中包含此信息来为用户提供有关错误的详细信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果 MAPI 提供由 _lppMAPIError_ 参数指向的 **MAPIERROR** 结构，则仅在 **GetLastError** 返回 S_OK。 有时 MAPI 无法确定上一个错误是什么，或者它仅能报告有关该错误的信息。 在这种情况下 **，GetLastError** 会改为在  _lppMAPIError_ 中返回指向 NULL 的指针。 
  
有关 **GetLastError** 方法的详细信息，请参阅 [MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MAPI 扩展错误](mapi-extended-errors.md)

