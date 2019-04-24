---
title: IMAPITableSetCollapseState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.SetCollapseState
api_type:
- COM
ms.assetid: 31325e8f-1cf9-49b2-8118-953996b0037f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7351457dc5b72cfc4a7ef9f91e9d33a80ca98c39
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328831"
---
# <a name="imapitablesetcollapsestate"></a>IMAPITable::SetCollapseState

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用以前对[IMAPITable:: GetCollapseState](imapitable-getcollapsestate.md)方法所保存的数据, 重新生成已分类表的当前展开或折叠状态。 
  
```cpp
HRESULT SetCollapseState(
ULONG ulFlags,
ULONG cbCollapseState,
LPBYTE pbCollapseState,
BOOKMARK FAR * lpbkLocation
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 保留必须为零。
    
 _cbCollapseState_
  
> 实时由_pbCollapseState_参数指向的结构中的字节数。 
    
 _pbCollapseState_
  
> 实时指向结构的指针, 这些结构包含重建表视图所需的数据。
    
 _lpbkLocation_
  
> 排除指向一个书签的指针, 该书签标识应在表中重新生成折叠或展开状态的行。 在对[IMAPITable:: GetCollapseState](imapitable-getcollapsestate.md)的调用中, 此书签和在_lpbInstanceKey_参数中传递的实例键可标识同一行。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功重建已分类表的状态。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作, 以阻止操作启动。 应允许正在进行的操作完成, 或者应已停止。
    
MAPI_E_UNABLE_TO_COMPLETE 
  
> 表无法完成已折叠或展开的视图的重建。
    
## <a name="remarks"></a>注解

**IMAPITable:: SetCollapseState**方法将重新建立表格视图的展开或折叠状态。 **SetCollapseState**和**GetCollapseState**协同工作, 如下所示: 
  
1. 当分类表的状态即将发生更改时, 将调用[IMAPITable:: GetCollapseState](imapitable-getcollapsestate.md) , 以保存与更改前的状态相关的所有数据。 
    
2. 若要将表的视图还原到其保存状态, 请调用**SetCollapseState** 。 由**GetCollapseState**保存的数据被传递给**SetCollapseState**。 **SetCollapseState**可以使用该数据还原状态。 
    
3. **SetCollapseState**作为输出参数返回一个书签, 该书签将一个标识为作为输入传递给**GetCollapseState**的实例键的同一行。
    
有关分类表的详细信息, 请参阅[排序和分类](sorting-and-categorization.md)。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您负责验证排序顺序和限制是否与在**GetCollapseState**调用时完全相同的。 如果进行了更改, 则不应调用**SetCollapseState** , 因为结果可能是不可预知的。 例如, 在调用**SetCollapseState**之前, 客户端调用**GetCollapseState** , 然后**SortTable**更改排序关键字时, 可能会发生这种情况。 为安全起见, 请先检查保存的数据是否仍然有效, 然后再继续进行还原。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要调用**SetCollapseState**, 必须先调用**GetCollapseState**。 对于这两种方法, 建立类别的排序顺序应相同。 如果排序顺序不同, 则**SetCollapseState**操作的结果是不可预知的。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[IMAPITable::FreeBookmark](imapitable-freebookmark.md)
  
[IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

