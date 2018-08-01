---
title: IMSLogonGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.GetLastError
api_type:
- COM
ms.assetid: 3e296f6d-4833-4c68-9b84-df0b09878474
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a865a751f3e274008c7004315906d6705ba55161
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775936"
---
# <a name="imslogongetlasterror"></a>IMSLogon::GetLastError

  
  
**适用于**： Outlook 
  
返回一个[MAPIERROR](mapierror.md)结构，其中包含上次消息存储对象发生的错误有关的信息。 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a>参数

 _hResult_
  
> [in]包含消息存储对象的上一个方法调用中生成的错误值 HRESULT 数据类型。
    
 _ulFlags_
  
> [in]返回控制的字符串类型的标志位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 
    
 _lppMAPIError_
  
> [输出]指向包含错误的版本、 组件及上下文信息返回**MAPIERROR**结构的指针的指针。 如果不没有返回任何**MAPIERROR** ， _lppMAPIError_参数可以设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
## <a name="remarks"></a>说明

**IMSLogon::GetLastError**方法用于检索要显示给用户有关从方法调用该消息存储对象返回的最后一个错误消息中的信息。 
  
若要释放所有 MAPI 返回**MAPIERROR**结构所分配的内存，客户端应用程序需要调用仅[MAPIFreeBuffer](mapifreebuffer.md)函数。 
  
从**GetLastError**返回的值必须是应用程序使用**MAPIERROR**S_OK。 即使的返回值是 S_OK，可能不会返回**MAPIERROR** 。 如果实现无法确定最后一个错误是什么，或者**MAPIERROR**不用于该错误， **GetLastError**返回一个指针为 NULL 中_lppMAPIError_改为。 
  
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

