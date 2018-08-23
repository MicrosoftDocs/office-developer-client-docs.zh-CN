---
title: HRESULT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HRESULT
api_type:
- COM
ms.assetid: b248ed11-3d8a-4d4c-9b84-fa5bee7979c7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a3e46732f9b74b9cdf2dc4c961e7b6b66e3d91d4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565226"
---
# <a name="hresult"></a>HRESULT

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
一个 32 位值，用来描述错误或警告。
  
```cpp
typedef LONG HRESULT;
```

## <a name="remarks"></a>注解

[SCODE](scode.md)数据类型相同的**HRESULT**数据类型。 
  
**HRESULT**值包含以下字段： 
  
- 指示严重级别 1 位代码，其中零表示成功，1 代表失败。
    
- 4 位保留的值。
    
- 11 位代码，指示错误或警告，也称为设施代码的责任。
    
- 一个 16 位代码描述该错误或警告。
    
大多数 MAPI 接口方法和函数返回可提供详细的原因构成的**HRESULT**值。 在 OLE 接口方法还广泛使用**HRESULT**值。 OLE 提供几个宏的**HRESULT**值和**SCODE**值之间进行转换的错误处理其他常见的数据类型。 
  
> [!NOTE]
> 64 位 MAPI 中**HRESULT**仍是 32 位值之一。 
  
有关 OLE 使用的**HRESULT**值的信息，请参阅*OLE 程序员参考*。 有关使用 MAPI 中的这些值的详细信息，请参阅[错误处理](error-handling-in-mapi.md)及任何以下接口方法： 
  
[IABLogon::GetLastError](iablogon-getlasterror.md)
  
[IMAPISupport::GetLastError](imapisupport-getlasterror.md)
  
[IMAPIControl::GetLastError](imapicontrol-getlasterror.md)
  
[IMAPITable::GetLastError](imapitable-getlasterror.md)
  
[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[IMAPIViewAdviseSink::OnPrint](imapiviewadvisesink-onprint.md)
  
## <a name="see-also"></a>另请参阅



[SCODE](scode.md)


[MAPI 数据类型](mapi-data-types.md)

