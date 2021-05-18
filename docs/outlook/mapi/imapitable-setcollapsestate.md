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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414065"
---
# <a name="imapitablesetcollapsestate"></a>IMAPITable::SetCollapseState

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用之前调用 [IMAPITable：：GetCollapseState](imapitable-getcollapsestate.md) 方法保存的数据重新生成分类表的当前展开或折叠状态。 
  
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
  
> 保留;必须为零。
    
 _cbCollapseState_
  
> [in]  _pbCollapseState_ 参数指向的结构中的字节数。 
    
 _pbCollapseState_
  
> [in]指向包含重新生成表视图所需的数据的结构的指针。
    
 _lpbkLocation_
  
> [out]指向书签的指针，该书签标识应重新构建折叠或展开状态在表格中的行。 此书签和在调用 [IMAPITable：：GetCollapseState](imapitable-getcollapsestate.md)时传入 _lpbInstanceKey_ 参数的实例键标识同一行。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功重建分类表的状态。
    
MAPI_E_BUSY 
  
> 正在进行另一个阻止操作启动的操作。 应允许完成或停止进行中的操作。
    
MAPI_E_UNABLE_TO_COMPLETE 
  
> 表无法完成折叠或展开视图的重新生成。
    
## <a name="remarks"></a>备注

**IMAPITable：：SetCollapseState** 方法重新建立表视图的展开或折叠状态。 **SetCollapseState** 和 **GetCollapseState** 协同工作，如下所示： 
  
1. 当分类表的状态即将更改时，将调用 [IMAPITable：：GetCollapseState](imapitable-getcollapsestate.md) 以保存与更改前状态相关的所有数据。 
    
2. 若要将表的视图还原到其保存状态，请调用 **SetCollapseState。** 由 **GetCollapseState** 保存的数据将传递给 **SetCollapseState**。 **SetCollapseState** 可以使用该数据还原状态。 
    
3. **SetCollapseState** 作为输出参数返回一个书签，该书签标识作为输入传递给 **GetCollapseState 的实例键相同的行**。
    
有关分类表的信息，请参阅排序 [和分类](sorting-and-categorization.md)。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您负责验证排序顺序和限制是否与 **GetCollapseState** 调用时的顺序和限制完全相同。 如果进行了更改， **则不应调用 SetCollapseState，** 因为结果可能无法预测。 例如，如果客户端调用 **GetCollapseState，** 然后 **SortTable** 在调用 **SetCollapseState** 之前更改排序键，则可能会发生这种情况。 若要安全，请在继续还原之前检查保存的数据是否仍然有效。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要调用 **SetCollapseState**，之前必须已调用 **GetCollapseState**。 对于这两种方法，建立类别的排序顺序应该相同。 如果排序顺序不同， **则 SetCollapseState** 操作的结果不可预测。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[IMAPITable::FreeBookmark](imapitable-freebookmark.md)
  
[IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

