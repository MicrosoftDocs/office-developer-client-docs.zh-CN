---
title: IABLogonGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.GetLastError
api_type:
- COM
ms.assetid: d157e29e-7731-4e47-b4a7-e8622b223001
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 311299b00143667b3f2fb22bd7be6c3a52c7141d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434247"
---
# <a name="iablogongetlasterror"></a>IABLogon::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关以前的通讯簿提供程序错误的信息。 
  
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
  
> 设置 MAPI_UNICODE 标志，通讯簿提供程序不支持 Unicode，或者MAPI_UNICODE设置该地址簿提供程序仅支持 Unicode。
    
## <a name="remarks"></a>备注

通讯簿提供程序实现 **GetLastError** 方法，以提供有关失败的之前方法调用的信息。 调用方可以通过在对话框中包含 **MAPIERROR** 结构的数据来为用户提供有关错误的详细信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果通讯簿提供程序提供结构并且仅在 **GetLastError** 返回 S_OK，您可以使用 _lppMAPIError_ 参数指向的 **MAPIERROR** 结构。 有时，通讯簿提供程序无法确定上一个错误是什么，或者没有更多关于错误的报告。 在这种情况下，通讯簿提供程序会改为在  _lppMAPIError_ 中返回指向 NULL 的指针。 
  
有关 **GetLastError** 方法的详细信息，请参阅 [MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

