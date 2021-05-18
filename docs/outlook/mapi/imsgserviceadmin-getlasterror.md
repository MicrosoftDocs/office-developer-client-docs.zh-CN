---
title: IMsgServiceAdminGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.GetLastError
api_type:
- COM
ms.assetid: 9e3c8d6e-74be-46a7-94ed-74a969caf165
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 302aebd0be78c833acf4f82d2bb815ba46ae6f77
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412140"
---
# <a name="imsgserviceadmingetlasterror"></a>IMsgServiceAdmin::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关邮件服务管理对象发生的最后一个错误的信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]HRESULT 数据类型，其中包含上一个方法调用生成的错误值。
    
 _ulFlags_
  
> [in]控制返回的字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> _lppMAPIError_ 参数中返回的 **MAPIERROR** 结构中的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。 
    
 _lppMAPIError_
  
> [out]指向返回的 **MAPIERROR** 结构的指针的指针，其中包含错误的版本、组件和上下文信息。 如果没有要返回的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 已MAPI_UNICODE邮件服务管理对象不支持 Unicode。
    
## <a name="remarks"></a>备注

**IMsgServiceAdmin：：GetLastError** 方法检索有关 [IMsgServiceAdmin](imsgserviceadminiunknown.md)方法调用返回的最后一个错误的信息。 客户端可以通过在对话框中包含此信息来为用户提供有关错误的详细信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果 MAPI 提供由 _lppMAPIError_ 参数指向的 **MAPIERROR** 结构，则只有在 **GetLastError** 返回值时，才能使用S_OK。 有时 MAPI 无法确定上一个错误是什么，或者没有更多关于错误的报告。 在这种情况下 **，GetLastError** 会改为在  _lppMAPIError_ 中返回指向 NULL 的指针。 
  
有关 **GetLastError** 方法的详细信息，请参阅 [使用扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

