---
title: IProfAdminGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.GetLastError
api_type:
- COM
ms.assetid: bb161d7b-ae5b-4f8e-a506-8346ac5e583d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b6964ecde3a78bd1e9ce0ae1dcab0342c5a21a03
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430771"
---
# <a name="iprofadmingetlasterror"></a>IProfAdmin::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关配置文件管理对象发生的上一个错误的信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]HRESULT 数据类型，其中包含在上一个方法调用中生成的错误值。
    
 _ulFlags_
  
> [in]控制返回的字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> _lppMAPIError_ 参数中返回的 [MAPIERROR](mapierror.md)结构中的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。 
    
 _lppMAPIError_
  
> [out]指向指向 **MAPIERROR** 结构的指针的指针，该结构包含错误的版本、组件和上下文信息。 如果没有要返回的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。
    
## <a name="remarks"></a>备注

**IProfAdmin：：GetLastError** 方法检索有关从配置文件管理对象的方法调用返回的最后一个错误的信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果 MAPI 提供由 _lppMAPIError_ 参数指向的 **MAPIERROR** 结构，则仅在 **GetLastError** 返回 S_OK。 有时 MAPI 无法确定上一个错误是什么，或者没有更多关于错误的报告。 在这种情况下，在  _lppMAPIError_ 中返回指向 NULL 的指针。 
  
若要释放 MAPI 为 **MAPIERROR** 结构分配的所有内存，请调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数。 
  
有关 **GetLastError** 方法的详细信息，请参阅 [使用扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)

