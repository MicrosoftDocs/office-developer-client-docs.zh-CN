---
title: IMAPITableAbort
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.Abort
api_type:
- COM
ms.assetid: 73291a5b-b626-494c-b5d9-f7709e34bac2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 68d40a6e152698554fcb88c6f7e5bfd4a7ff0ce3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574004"
---
# <a name="imapitableabort"></a>IMAPITable::Abort

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
停止当前正在进行任何异步操作表。
  
```cpp
HRESULT Abort( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 一个或多个异步操作已停止。
    
MAPI_E_UNABLE_TO_ABORT 
  
> 异步操作正在编写中，无法停止或已完成。
    
## <a name="remarks"></a>注解

**IMAPITable::Abort**方法停止当前正在进行的任何异步操作。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要找出异步操作是否正在进行，请调用[IMAPITable::GetStatus](imapitable-getstatus.md)方法。 
  
如果**中止**暂停处理[IMAPITable::Restrict](imapitable-restrict.md)方法的调用，表的状态将时处理**中止**的呼叫的时间。 
  
如果**中止**暂停处理[IMAPITable::SortTable](imapitable-sorttable.md)方法的调用，表的排序顺序不会受到影响，并保持前**SortTable**呼叫。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::GetStatus](imapitable-getstatus.md)
  
[IMAPITable::Restrict](imapitable-restrict.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

