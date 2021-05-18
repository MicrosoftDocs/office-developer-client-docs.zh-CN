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
  
在表上的一个或多个异步操作完成之前暂停处理。
  
```cpp
HRESULT WaitForCompletion(
ULONG ulFlags,
ULONG ulTimeout,
ULONG FAR * lpulTableStatus
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 保留;必须为零。
    
 _ulTimeout_
  
> [in]等待异步操作完成的最大毫秒数。 若要无限期地等待直到完成，请设置  _ulTimeout_ 以0xFFFFFFFF。 
    
 _lpulTableStatus_
  
> [in， out]在输入时，有效指针或 NULL。 在输出上，如果  _lpulTableStatus_ 是有效的指针，则它指向表的最新状态。 如果  _lpulTableStatus_ 为 NULL，则不返回任何状态信息。 如果 **WaitForCompletion** 返回不成功的 HRESULT 值，  _则 lpulTableStatus_ 的内容未定义。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 等待操作成功。
    
MAPI_E_NO_SUPPORT 
  
> 该表不支持等待异步操作完成。
    
MAPI_E_TIMEOUT 
  
> 异步操作没有在指定的时间完成。
    
## <a name="remarks"></a>备注

**IMAPITable：：WaitForCompletion 方法将暂停** 处理，直到表当前正在执行的任何异步操作完成。 **WaitForCompletion** 可以允许异步操作完全完成或运行一定数量的毫秒，如  _ulTimeout_ 所指示，然后再中断。 若要检测正在进行中的异步操作，请调用 [IMAPITable：：GetStatus](imapitable-getstatus.md) 方法。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::GetRowCount](imapitable-getrowcount.md)
  
[IMAPITable::GetStatus](imapitable-getstatus.md)
  
[IMAPITable::Restrict](imapitable-restrict.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

