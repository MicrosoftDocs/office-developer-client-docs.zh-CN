---
title: IMAPIControlGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIControl.GetLastError
api_type:
- COM
ms.assetid: 83290b8e-fffc-41c8-a01e-578d130b65c5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ef5fee7a2e84133f88a00703f7602831d26e3d3d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594724"
---
# <a name="imapicontrolgetlasterror"></a>IMAPIControl::GetLastError

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前一个按钮控件错误的信息。 
  
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
  
> [输出]指向包含错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。 _LppMAPIError_参数可以设置为 NULL，如果提供程序不能提供一个**MAPIERROR**相应的信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
## <a name="remarks"></a>注解

服务提供商实现**IMAPIControl::GetLastError**方法以提供有关失败的前一个方法调用的信息。 MAPI 可以通过在消息或对话框中显示的数据从**MAPIERROR**结构授予用户有关错误的详细的信息。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

不需要在每个错误的**MAPIERROR**结构中包含的信息。 它可能不确定前面的错误是什么。 如果您有信息，则返回 S_OK 和适当的数据**MAPIERROR**结构中。 如果没有信息，则返回 S_OK 和指针为 NULL _lppMAPIError_参数。 
  
有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPIControl : IUnknown](imapicontroliunknown.md)

