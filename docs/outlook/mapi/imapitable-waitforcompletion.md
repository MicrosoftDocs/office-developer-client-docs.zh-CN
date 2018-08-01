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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c7859e033924786e415f9faa9f75021ea47968c6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775723"
---
# <a name="imapitablewaitforcompletion"></a>IMAPITable::WaitForCompletion

  
  
**适用于**： Outlook 
  
挂起处理，直到完成一个或多个异步正在进行的操作在表上。
  
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
  
> [in]最大等待操作完成的异步操作的毫秒数。 若要完成之前无限期等待，设置为 0xFFFFFFFF _ulTimeout_ 。 
    
 _lpulTableStatus_
  
> [传入、 传出]在输入有效的指针或 NULL。 输出，如果_lpulTableStatus_是有效的指针，它指向表的最新状态。 如果_lpulTableStatus_为 NULL，则不返回任何状态信息。 如果**WaitForCompletion**返回一个失败的 HRESULT 值，则_lpulTableStatus_的内容是未定义。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 等待操作已成功。
    
MAPI_E_NO_SUPPORT 
  
> 表不支持的异步操作完成后的等待。
    
MAPI_E_TIMEOUT 
  
> 在指定时间的异步操作未完成。
    
## <a name="remarks"></a>说明

**IMAPITable::WaitForCompletion**方法挂起处理，直到表当前正在进行任何异步操作完成。 **WaitForCompletion**可以允许异步操作到完全完成或运行一定数量的毫秒，由_ulTimeout_之前被打扰。 若要检测正在进行的异步操作，请调用[IMAPITable::GetStatus](imapitable-getstatus.md)方法。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::GetRowCount](imapitable-getrowcount.md)
  
[IMAPITable::GetStatus](imapitable-getstatus.md)
  
[IMAPITable::Restrict](imapitable-restrict.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

