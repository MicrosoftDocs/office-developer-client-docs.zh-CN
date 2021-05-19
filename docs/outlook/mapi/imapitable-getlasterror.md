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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2444ea7e05367423e7920be3a871c2ab68aad76d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419000"
---
# <a name="imapitablegetlasterror"></a>IMAPITable::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关表上上一个错误的信息。 
  
```cpp
HRESULT GetLastError(
HRESULT hResult,
ULONG ulFlags,
LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]包含上一个方法调用中生成的错误的 HRESULT。
    
 _ulFlags_
  
> [in]控制返回的字符串类型的标志的位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> _lppMAPIError_ 参数中返回的 **MAPIERROR** 结构中的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。 
    
 _lppMAPIError_
  
> [out]指向返回的 **MAPIERROR** 结构的指针，其中包含错误的版本、组件和上下文信息。 如果无法提供包含相应信息的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，并且实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
## <a name="remarks"></a>备注

**IMAPITable：：GetLastError** 方法返回有关失败之前的方法调用的详细信息（如果可用）。 此信息可以显示在消息或对话框中。 
  
## <a name="notes-to-callers"></a>给调用方的说明

每当需要向用户显示有关错误的信息时，调用 **GetLastError。** 
  
如果 table 对象仅在 **GetLastError** 返回值时提供一个 [MAPIERROR](mapierror.md)结构，则您可以使用 _lppMAPIError_ 参数S_OK。 有时，表实现无法确定上一个错误是什么，或者没有更多关于错误的报告。 在这种情况下  _，lppMAPIError_ 中的指针设置为 NULL。 
  
若要释放为 **MAPIERROR** 结构分配的所有内存，请调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数。 
  
有关 **GetLastError** 方法的详细信息，请参阅 [MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

