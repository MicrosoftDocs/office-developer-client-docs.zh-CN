---
title: IMAPITableWaitForCompletion
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.WaitForCompletion
api_type:
- COM
ms.assetid: 7663c640-396e-4720-9345-370d0856bd49
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 778ff8f36478740e5ee23ba439db1e328eca2e06
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407058"
---
# <a name="imapitablewaitforcompletion"></a>IMAPITable::WaitForCompletion

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在对表进行的一个或多个异步操作完成之前, 挂起处理。
  
```cpp
HRESULT WaitForCompletion(
ULONG ulFlags,
ULONG ulTimeout,
ULONG FAR * lpulTableStatus
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 保留必须为零。
    
 _ulTimeout_
  
> 实时要等待异步操作或操作完成的最大毫秒数。 若要无限期地等待完成, 请将_ulTimeout_设置为0xffffffff。 
    
 _lpulTableStatus_
  
> [in, out]在输入时, 可以是有效的指针或 NULL。 在输出时, 如果_lpulTableStatus_是有效的指针, 则指向表的最新状态。 如果_lpulTableStatus_为 NULL, 则不返回任何状态信息。 如果**WaitForCompletion**返回的 HRESULT 值不成功, 则_lpulTableStatus_的内容未定义。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 等待操作成功。
    
MAPI_E_NO_SUPPORT 
  
> 该表不支持等待异步操作的完成。
    
MAPI_E_TIMEOUT 
  
> 未在指定时间内完成异步操作或操作。
    
## <a name="remarks"></a>说明

**IMAPITable:: WaitForCompletion**方法将挂起处理, 直到对表的当前正下方的任何异步操作完成。 **WaitForCompletion**可以允许异步操作完全完成或运行一定的毫秒数 (由_ulTimeout_指示), 然后才会被中断。 若要检测正在进行的异步操作, 请调用[IMAPITable:: GetStatus](imapitable-getstatus.md)方法。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::GetRowCount](imapitable-getrowcount.md)
  
[IMAPITable::GetStatus](imapitable-getstatus.md)
  
[IMAPITable::Restrict](imapitable-restrict.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

