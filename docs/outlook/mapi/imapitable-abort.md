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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328945"
---
# <a name="imapitableabort"></a>IMAPITable::Abort

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
停止当前对表进行的所有异步操作。
  
```cpp
HRESULT Abort( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 一个或多个异步操作已停止。
    
MAPI_E_UNABLE_TO_ABORT 
  
> 正在进行异步操作, 无法停止或已完成。
    
## <a name="remarks"></a>注解

**IMAPITable:: Abort**方法会停止当前正在进行的任何异步操作。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要了解是否正在进行异步操作, 请调用[IMAPITable:: GetStatus](imapitable-getstatus.md)方法。 
  
如果**Abort 中止**对[IMAPITable:: Restrict](imapitable-restrict.md)方法的调用的处理, 则表的状态将与处理**中止**调用时的状态相同。 
  
如果**Abort 中止**对[IMAPITable:: SortTable](imapitable-sorttable.md)方法的调用的处理, 则表的排序顺序不受影响, 并保持在**SortTable**调用之前。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::GetStatus](imapitable-getstatus.md)
  
[IMAPITable::Restrict](imapitable-restrict.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

