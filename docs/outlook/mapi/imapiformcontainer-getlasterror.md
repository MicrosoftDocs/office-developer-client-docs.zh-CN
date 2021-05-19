---
title: IMAPIFormContainerGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.GetLastError
api_type:
- COM
ms.assetid: 04952b51-f005-4933-a1d1-695c6dc736cc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e020c66a46f1f195a5731ef1cb3f4b0488162a2b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415668"
---
# <a name="imapiformcontainergetlasterror"></a>IMAPIFormContainer::GetLastError

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关表单容器对象生成的上一个错误的信息。 
  
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
  
> [out]指向返回的 **MAPIERROR** 结构的指针的指针，其中包含错误的版本、组件和上下文信息。 如果没有要返回的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置MAPI_UNICODE **GetLastError** 不支持 Unicode，或者未MAPI_UNICODE **GetLastError** 仅支持 Unicode。 
    
## <a name="remarks"></a>备注

**IMAPIFormContainer：：GetLastError** 方法提供有关失败之前的方法调用的信息。 调用方可以通过在对话框中包含 **MAPIERROR** 结构的数据来为用户提供有关错误的详细信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果 MAPI 仅在 **GetLastError** 返回值时提供一个 **MAPIERROR** 结构，则您可以使用 _lppMAPIError_ 参数S_OK。 有时 MAPI 无法确定上一个错误是什么，或者没有更多关于错误的报告。 在这种情况下，将改为在  _lppMAPIError_ 中返回指向 NULL 的指针。 
  
有关 **GetLastError** 方法的详细信息，请参阅 [使用扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[IMAPIFormContainer : IUnknown](imapiformcontaineriunknown.md)

