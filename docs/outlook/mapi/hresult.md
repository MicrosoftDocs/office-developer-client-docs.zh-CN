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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 64fcbebbd71bc3f478f36c711e49db9a3518ef9a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435017"
---
# <a name="hresult"></a>HRESULT

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
用于描述错误或警告的 32 位值。
  
```cpp
typedef LONG HRESULT;
```

## <a name="remarks"></a>备注

**HRESULT** 数据类型与 [SCODE](scode.md)代码数据类型。 
  
**HRESULT** 值由以下字段组成： 
  
- 指示严重性的 1 位代码，其中 0 表示成功，1 表示失败。
    
- 4 位保留值。
    
- 指示错误或警告责任的 11 位代码，也称为设备代码。
    
- 描述错误或警告的 16 位代码。
    
大多数 MAPI 接口方法和函数都返回 **HRESULT** 值以提供详细的原因形成。 **HRESULT** 值也广泛使用在 OLE 接口方法中。 OLE 提供了多个宏，用于在 **HRESULT** 值和 **SCODE** 值之间转换，这是另一种数据类型错误处理的常用方法。 
  
> [!NOTE]
> 在 64 位 MAPI 中 **，HRESULT** 仍是 32 位值。 
  
有关 OLE 使用 **HRESULT** 值的信息，请参阅 *《OLE 程序员参考》。* 有关在 MAPI 中使用这些值的详细信息，请参阅 [错误处理](error-handling-in-mapi.md) 和以下任一接口方法： 
  
[IABLogon::GetLastError](iablogon-getlasterror.md)
  
[IMAPISupport::GetLastError](imapisupport-getlasterror.md)
  
[IMAPIControl::GetLastError](imapicontrol-getlasterror.md)
  
[IMAPITable::GetLastError](imapitable-getlasterror.md)
  
[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[IMAPIViewAdviseSink::OnPrint](imapiviewadvisesink-onprint.md)
  
## <a name="see-also"></a>另请参阅



[SCODE](scode.md)


[MAPI 数据类型](mapi-data-types.md)

