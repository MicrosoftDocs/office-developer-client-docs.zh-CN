---
title: IPersistMessageGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.GetLastError
api_type:
- COM
ms.assetid: 32cc3a1f-1310-4788-b0f4-93c1e4940f37
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a39deb57a24b3a89ee10020a6442bcb1bca612a3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575306"
---
# <a name="ipersistmessagegetlasterror"></a>IPersistMessage::GetLastError

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回一个[MAPIERROR](mapierror.md)结构，其中包含有关表单对象中前面的错误的信息。 
  
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
  
> [输出]指向包含错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。 _LppMAPIError_参数可以设置为 NULL，如果窗体不能提供相应**MAPIERROR**结构的信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志通讯簿提供程序不支持 Unicode，或未设置 MAPI_UNICODE 和通讯簿提供程序支持仅 Unicode。
    
## <a name="remarks"></a>注解

表单对象实现**IPersistMessage::GetLastError**方法以提供有关失败的前一个方法调用的信息。 窗体查看者可以通过在对话框中包含的数据从[MAPIERROR](mapierror.md)结构为其用户提供有关错误的详细信息。 
  
调用**GetLastError**不会影响表单的状态。 **GetLastError**返回时，窗体将保持之前拨打电话的状态。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果表单提供一个指向_lppMAPIError_参数**时出错**，则返回 S_OK 时，才可以使用**MAPIERROR**结构。 有时表单无法确定最后一个错误已或某种更多有关错误报告。 在此情况下，窗体返回一个指针为 NULL 中_lppMAPIError_相反。 
  
有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IPersistMessage : IUnknown](ipersistmessageiunknown.md)

