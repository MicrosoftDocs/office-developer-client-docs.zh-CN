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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 250074b28b98269df58fecfcb2d178f73e26c571
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775995"
---
# <a name="iprofadmingetlasterror"></a>IProfAdmin::GetLastError

  
  
**适用于**： Outlook 
  
返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的配置文件管理对象发生的错误的信息。 
  
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
  
> 返回_lppMAPIError_参数中的[MAPIERROR](mapierror.md)结构中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 
    
 _lppMAPIError_
  
> [输出]指向包含错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。 如果不没有返回任何**MAPIERROR**结构， _lppMAPIError_参数可以设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
## <a name="remarks"></a>备注

**IProfAdmin::GetLastError**方法检索信息从配置文件管理对象方法调用返回的最后一个错误。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以使用**MAPIERROR**结构中，如果 MAPI 提供一个，由指向_lppMAPIError_参数才**GetLastError**返回 S_OK。 有时 MAPI 无法确定最后一个错误已或某种更多有关错误报告。 在此情况下，为 NULL 的指针返回_lppMAPIError_。 
  
释放所有 MAPI **MAPIERROR**结构所分配的内存，调用[MAPIFreeBuffer](mapifreebuffer.md)函数。 
  
有关**GetLastError**方法的详细信息，请参阅[使用扩展的错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IProfAdmin: IUnknown](iprofadminiunknown.md)

