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
  
一个用于描述错误或警告的32位值。
  
```cpp
typedef LONG HRESULT;
```

## <a name="remarks"></a>说明

**HRESULT**数据类型与[SCODE](scode.md)数据类型相同。 
  
**HRESULT**值包含以下字段: 
  
- 表示严重度的1位代码, 其中0表示成功, 1 表示失败。
    
- 一个4位保留值。
    
- 11位代码, 用于指示对错误或警告 (也称为设施代码) 的责任。
    
- 一个用于描述错误或警告的16位代码。
    
大多数 MAPI 接口方法和函数返回**HRESULT**值, 以提供详细的原因构成。 **HRESULT**值也在 OLE 接口方法中广泛使用。 OLE 提供了几个用于在**HRESULT**值和**SCODE**值之间进行转换的宏, 这是用于错误处理的另一种常见数据类型。 
  
> [!NOTE]
> 在64位 MAPI 中, **HRESULT**仍为32位值。 
  
若要了解有关**HRESULT**值的 OLE 用法的信息, 请参阅*ole 程序员参考*。 有关在 MAPI 中使用这些值的详细信息, 请参阅[错误处理](error-handling-in-mapi.md)和以下任何接口方法: 
  
[IABLogon::GetLastError](iablogon-getlasterror.md)
  
[IMAPISupport::GetLastError](imapisupport-getlasterror.md)
  
[IMAPIControl::GetLastError](imapicontrol-getlasterror.md)
  
[IMAPITable::GetLastError](imapitable-getlasterror.md)
  
[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[IMAPIViewAdviseSink::OnPrint](imapiviewadvisesink-onprint.md)
  
## <a name="see-also"></a>另请参阅



[SCODE](scode.md)


[MAPI 数据类型](mapi-data-types.md)

