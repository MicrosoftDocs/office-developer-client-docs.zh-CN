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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328998"
---
# <a name="imapitablegetlasterror"></a>IMAPITable::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个[MAPIERROR](mapierror.md)结构, 其中包含有关表格上一个错误的信息。 
  
```cpp
HRESULT GetLastError(
HRESULT hResult,
ULONG ulFlags,
LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> 实时HRESULT 包含在上一方法调用中生成的错误。
    
 _ulFlags_
  
> 实时用于控制返回的字符串的类型的标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 在_lppMAPIError_参数中返回的**MAPIERROR**结构中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。 
    
 _lppMAPIError_
  
> 排除指向指向包含错误的版本、组件和上下文信息的返回的**MAPIERROR**结构的指针的指针。 如果无法提供具有相应信息的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
## <a name="remarks"></a>注解

**IMAPITable:: GetLastError**方法返回有关以前的方法调用失败的详细信息 (如果有)。 此信息可以显示在邮件或对话框中。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在需要向用户显示有关错误的信息时, 请调用**GetLastError** 。 
  
如果 table 对象仅在**GetLastError**返回 S_OK 时仅提供一个 MAPIERROR 结构, 则可以使用_lppMAPIError_参数所指向的[](mapierror.md)结构。 有时, 表实现无法确定最后一个错误是什么, 或者对错误报告没有什么更多的报告。 在这种情况下, _lppMAPIError_中的指针设置为 NULL。 
  
若要释放为**MAPIERROR**结构分配的所有内存, 请调用[MAPIFreeBuffer](mapifreebuffer.md)函数。 
  
有关**GetLastError**方法的详细信息, 请参阅[MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

