---
title: IMAPITableGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.GetLastError
api_type:
- COM
ms.assetid: 832e2c18-ddba-4d18-a391-710d21fe23e6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b8ee83ad550106ae82f3308b9ef5692f66f5f5b6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775706"
---
# <a name="imapitablegetlasterror"></a>IMAPITable::GetLastError

  
  
**适用于**： Outlook 
  
返回[MAPIERROR](mapierror.md)结构包含有关在表格的上一个错误。 
  
```cpp
HRESULT GetLastError(
HRESULT hResult,
ULONG ulFlags,
LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]HRESULT 包含在前面的方法调用中生成错误。
    
 _ulFlags_
  
> [in]位掩码的标志，控制返回的字符串的类型。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 
    
 _lppMAPIError_
  
> [输出]为包含用于错误的版本、 组件及上下文信息的返回**MAPIERROR**结构指针的指针。 _LppMAPIError_参数可以设置为 NULL，如果不能提供一个**MAPIERROR**相应的信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现仅支持 Unicode。
    
## <a name="remarks"></a>说明

**IMAPITable::GetLastError**方法返回的详细的信息，如果可用，有关失败的前一个方法调用。 可以在一条消息或对话框中显示此信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

无论何时需要向用户显示错误的信息，请调用**时出错**。 
  
您可以利用[MAPIERROR](mapierror.md)结构_lppMAPIError_参数指向如果 table 对象提供一个仅当**时出错**，则返回 S_OK。 有时表实现无法确定最后一个错误已或某种更多有关错误报告。 在此情况下，在_lppMAPIError_指针设置为 NULL。 
  
若要解除所有**MAPIERROR**结构分配的内存，调用[MAPIFreeBuffer](mapifreebuffer.md)函数。 
  
有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

