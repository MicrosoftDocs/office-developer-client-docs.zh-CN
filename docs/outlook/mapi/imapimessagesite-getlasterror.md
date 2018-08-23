---
title: IMAPIMessageSiteGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.GetLastError
api_type:
- COM
ms.assetid: 7ea282d7-388a-4f05-9780-f8dbc5c5d395
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3426fd29090a6ab1bb0e66f9bb746e84abe3a25e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589446"
---
# <a name="imapimessagesitegetlasterror"></a>IMAPIMessageSite::GetLastError

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的错误消息网站对象发生的信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]HRESULT 值，它包含在以前的方法调用中生成的错误值。
    
 _ulFlags_
  
> [in]返回控制的字符串类型的标志位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 
    
 _lppMAPIError_
  
> [输出]指向包含错误的版本、 组件及上下文信息返回**MAPIERROR**结构的指针的指针。 如果不没有返回任何**MAPIERROR**结构，此参数可以设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_BAD_CHARWIDTH
  
> 既设置了 MAPI_UNICODE 标志**GetLastError**不支持 Unicode，或未设置 MAPI_UNICODE 和**GetLastError**支持仅 Unicode。 
    
## <a name="remarks"></a>注解

**IMAPIMessageSite::GetLastError**方法提供有关失败的前一个方法调用的信息。 呼叫者可以向其用户提供有关错误的详细信息通过在对话框中包括的**MAPIERROR**结构中的数据。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以利用**MAPIERROR**结构_lppMAPIError_参数指向如果 MAPI 提供一个仅当**时出错**，则返回 S_OK。 有时 MAPI 无法确定最后一个错误，或某种更多有关错误报告。 在这种情况下，为 NULL 的指针被返回在_lppMAPIError_中。 
  
有关**GetLastError**方法的详细信息，请参阅[使用扩展的错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)

