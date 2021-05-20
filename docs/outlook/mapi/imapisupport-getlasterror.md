---
title: IMAPISupportGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.GetLastError
api_type:
- COM
ms.assetid: 5b4290d9-230f-416a-9644-188578565c7b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c34c175c43ada03e982f08a27f675448ea24a567
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438545"
---
# <a name="imapisupportgetlasterror"></a>IMAPISupport::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个支持对象错误的信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]对在上一个方法调用中为支持对象生成的错误值的句柄。
    
 _ulFlags_
  
> [in]控制返回的字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> _lppMAPIError_ 参数中返回的 **MAPIERROR** 结构中的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。 
    
 _lppMAPIError_
  
> [out]指向指向 **MAPIERROR** 结构的指针的指针，该结构包含错误的版本、组件和上下文信息。 如果无法提供包含相应错误信息的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置MAPI_UNICODE MAPI 不支持 Unicode，或者未MAPI_UNICODE MAPI 仅支持 Unicode。
    
## <a name="remarks"></a>备注

**IMAPISupport：：GetLastError** 方法针对所有支持对象实现。 调用方可以通过在对话框中包含 **MAPIERROR** 结构的数据来为用户提供有关错误的详细信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

只有当 **GetLastError** 返回值时，才能在 _lppMAPIError_ 参数中使用指向 **MAPIERROR** 结构的指针（如果 MAPI 提供了S_OK）。 有时 MAPI 无法确定上一个错误是什么，或者它仅能报告有关该错误的信息。 在这种情况下  _，lppMAPIError_ 会改为返回指向 NULL 的指针。 
  
有关 **GetLastError** 方法的详细信息，请参阅 [MAPI 扩展错误](mapi-extended-errors.md)。
  
若要释放 MAPI 分配的所有内存，请为返回的 **MAPIERROR** 结构调用 [MAPIFreeBuffer](mapifreebuffer.md)函数。 
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)


[MAPI 扩展错误](mapi-extended-errors.md)

