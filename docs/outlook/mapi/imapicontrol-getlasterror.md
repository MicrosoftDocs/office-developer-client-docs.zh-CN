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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 10ac4e33b3f734ec2ce3205aa1897e0418cb563d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421149"
---
# <a name="imapicontrolgetlasterror"></a>IMAPIControl::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个按钮控件错误的信息。 
  
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
  
> [out]指向 **MAPIERROR** 结构的指针的指针，其中包含错误的版本、组件和上下文信息。 如果提供程序无法向 **MAPIERROR** 结构提供适当的信息，则 _lppMAPIError_ 参数可以设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
## <a name="remarks"></a>备注

服务提供商实现 **IMAPIControl：：GetLastError** 方法，以提供有关失败的之前方法调用的信息。 MAPI 可以通过在消息或对话框中显示 **MAPIERROR** 结构的数据来为用户提供有关错误的详细信息。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

无需包含针对每个错误的 **MAPIERROR** 结构的信息。 可能无法确定上一错误是什么。 如果你有信息，请S_OK **MAPIERROR** 结构中的数据和相应的数据。 如果没有可用信息，则返回 S_OK，并返回  _lppMAPIError_ 参数的 NULL 指针。 
  
有关 **GetLastError** 方法的详细信息，请参阅 [MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPIControl : IUnknown](imapicontroliunknown.md)

