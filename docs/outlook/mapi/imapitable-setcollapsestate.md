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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 51c239897e5e225a0765f78404526e2836371f30
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567900"
---
# <a name="imapitablesetcollapsestate"></a>IMAPITable::SetCollapseState

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
重建使用以前[IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)方法调用已保存的数据分类表的当前展开还是折叠状态。 
  
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
  
> [in]由_pbCollapseState_参数指向的结构中的字节数。 
    
 _pbCollapseState_
  
> [in]指针指向包含重建表视图所需的数据的结构。
    
 _lpbkLocation_
  
> [输出]确定应频率重建折叠或展开状态表中的行的书签的指针。 该书签和[IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)调用_lpbInstanceKey_参数中传递的实例密钥标识同一行。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功重建分类的表的状态。
    
MAPI_E_BUSY 
  
> 正在进行中，可以防止启动操作是另一个操作。 应允许正在进行的操作完成或应停止。
    
MAPI_E_UNABLE_TO_COMPLETE 
  
> 表无法完成重建折叠或展开视图。
    
## <a name="remarks"></a>注解

**IMAPITable::SetCollapseState**方法重建表视图展开或折叠状态。 **SetCollapseState**和**GetCollapseState**协同工作，如下所示： 
  
1. 分类表的状态为将要更改，当[IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)称为保存所有到更改之前的状态相关的数据。 
    
2. 若要向其保存的状态还原表的视图，请调用**SetCollapseState** 。 由**GetCollapseState**保存数据传递到**SetCollapseState**。 **SetCollapseState**是能够使用该数据还原状态。 
    
3. **SetCollapseState**输出参数的形式返回标识作为输入传递给**GetCollapseState**实例键所在的行的书签。
    
有关分类表的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

您负责验证的排序顺序和限制完全相同时**GetCollapseState**呼叫的时间。 如果已进行更改，应不会由于结果不可预知调用**SetCollapseState** 。 如果，例如，在客户端调用**GetCollapseState** ，然后选择**SortTable**调用**SetCollapseState**之前更改排序关键字，则可以发生此错误。 为安全起见，检查仍然有效，然后再继续完成还原操作保存的数据。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要调用**SetCollapseState**，您必须以前称为**GetCollapseState**。 建立类别的排序次序应为这两种方法相同。 如果排序次序不同， **SetCollapseState**操作的结果将无法预料。 
  
## <a name="see-also"></a>另请参阅



[IMAPITable::CreateBookmark](imapitable-createbookmark.md)
  
[IMAPITable::FreeBookmark](imapitable-freebookmark.md)
  
[IMAPITable::GetCollapseState](imapitable-getcollapsestate.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

