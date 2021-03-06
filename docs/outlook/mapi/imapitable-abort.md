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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 74c307fca27f1adec18d236792f8a58d97e33ec5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406148"
---
# <a name="imapitableabort"></a>IMAPITable::Abort

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
停止表当前正在执行的任何异步操作。
  
```cpp
HRESULT Abort( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 一个或多个异步操作已停止。
    
MAPI_E_UNABLE_TO_ABORT 
  
> 异步操作正在进行中，无法停止或已完成。
    
## <a name="remarks"></a>备注

**IMAPITable：：Abort** 方法将停止当前进行的任何异步操作。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要了解异步操作是否正在进行，请调用 [IMAPITable：：GetStatus](imapitable-getstatus.md) 方法。 
  
如果 **Abort** 停止处理对 [IMAPITable：：Restrict](imapitable-restrict.md) 方法的调用，则表的状态将和 **处理 Abort** 调用时的状态一样。 
  
如果 **Abort** 停止处理对 [IMAPITable：：SortTable](imapitable-sorttable.md) 方法的调用，则表的排序顺序不受影响，并且保持与 **SortTable** 调用之前一样。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::GetStatus](imapitable-getstatus.md)
  
[IMAPITable::Restrict](imapitable-restrict.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

