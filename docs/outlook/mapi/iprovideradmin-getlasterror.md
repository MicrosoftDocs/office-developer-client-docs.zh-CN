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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f00418efa068ea81fab94605cbdfd139e24bb4a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776018"
---
# <a name="iprovideradmingetlasterror"></a>IProviderAdmin::GetLastError

  
  
**适用于**： Outlook 
  
返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的提供程序的管理对象发生的错误的信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]包含上一方法调用中生成的错误值 HRESULT 数据类型。
    
 _ulFlags_
  
> [in]返回控制的字符串类型的标志位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 中**MAPIERROR** _lppMAPIError_参数中返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 
    
 _lppMAPIError_
  
> [输出]指向包含错误的版本、 组件及上下文信息返回**MAPIERROR**结构的指针的指针。 如果不没有返回任何**MAPIERROR** ， _lppMAPIError_参数可以设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志**GetLastError**不支持 Unicode，或未设置 MAPI_UNICODE 和**GetLastError**支持仅 Unicode。 
    
## <a name="remarks"></a>说明

**IProviderAdmin::GetLastError**方法提供有关失败的前一个方法调用的信息。 呼叫者可以向其用户提供有关错误的详细信息通过在对话框中包括的**MAPIERROR**结构中的数据。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以使用**MAPIERROR**结构中，如果 MAPI 提供一个，仅当**时出错**，则返回 S_OK _lppMAPIError_参数，指向。 有时 MAPI 无法确定最后一个错误已或某种更多有关错误报告。 在这种情况下，为 NULL 的指针被返回在_lppMAPIError_中。 
  
有关**GetLastError**方法的详细信息，请参阅[使用扩展的错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IProviderAdmin : IUnknown](iprovideradminiunknown.md)

