---
title: IMAPIViewContextGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.GetLastError
api_type:
- COM
ms.assetid: 3306e37a-2500-4281-96c3-ca0d5c81909d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f7455e9013f3bd9460ae5f4d876c135594840b68
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775739"
---
# <a name="imapiviewcontextgetlasterror"></a>IMAPIViewContext::GetLastError

  
  
**适用于**： Outlook 
  
返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面对视图上下文对象发生的错误的信息。 
  
```cpp
HRESULT GetLastError(
HRESULT hResult,
ULONG ulFlags,
LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]包含上一方法调用中生成的错误值的 HRESULT 数据类型。
    
 _ulFlags_
  
> [in]返回的标志的控制的字符串类型的位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 
    
 _lppMAPIError_
  
> [输出]为包含用于错误的版本、 组件及上下文信息返回**MAPIERROR**结构指针的指针。 如果不没有返回任何**MAPIERROR**结构，此参数可以设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_BAD_CHARWIDTH 
  
> 可以设置该 MAPI_UNICODE 标记**GetLastError**不支持 Unicode，或未设置 MAPI_UNICODE 和**GetLastError**仅支持 Unicode。 
    
## <a name="remarks"></a>备注

**IMAPIViewContext::GetLastError**方法提供有关失败的前一个方法调用的信息。 呼叫者可以向其用户提供有关错误的详细信息通过在对话框中包括的**MAPIERROR**结构中的数据。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以利用**MAPIERROR**结构_lppMAPIError_参数指向如果 MAPI 提供一个仅当**时出错**，则返回 S_OK。 有时 MAPI 无法确定最后一个错误已或某种更多有关错误报告。 在这种情况下，为 NULL 的指针被返回在_lppMAPIError_中。 
  
有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPIViewContext: IUnknown](imapiviewcontextiunknown.md)

