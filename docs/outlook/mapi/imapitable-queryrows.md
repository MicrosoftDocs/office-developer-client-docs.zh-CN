---
title: IMAPITableQueryRows
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.QueryRows
api_type:
- COM
ms.assetid: f26384f1-467e-4343-92b3-0425da9d2123
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 179d76b56c1ba9b40768c691d0b1555377f7adb7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595046"
---
# <a name="imapitablequeryrows"></a>IMAPITable::QueryRows

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
从表中，开始在当前光标位置返回一个或多个行。
  
```cpp
HRESULT QueryRows(
LONG lRowCount,
ULONG ulFlags,
LPSRowSet FAR * lppRows
);
```

## <a name="parameters"></a>参数

 _lRowCount_
  
> [in]要返回的行的最大数量。
    
 _ulFlags_
  
> [in]控制如何返回行的标志的位掩码。 可以设置以下标记：
    
TBL_NOADVANCE 
  
> 防止由于行检索执行光标。 如果设置 TBL_NOADVANCE 标志，则返回的第一行的指针指向。 如果未设置 TBL_NOADVANCE 标志，光标指向关注返回的最后一行的行。
    
 _lppRows_
  
> [输出]为存放的表格行[SRowSet](srowset.md)结构指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回行。
    
MAPI_E_BUSY 
  
> 正在阻止从起始行检索操作是另一个操作。 应允许正在进行的操作完成或应停止。
    
MAPI_E_INVALID_PARAMETER 
  
> _IRowCount_参数设置为零。 
    
## <a name="remarks"></a>注解

**IMAPITable::QueryRows**方法获取表中的一个或多个数据行。 _IRowCount_参数的值会影响检索的起始点。 如果_IRowCount_为正数，则读取行时向前，当前位置开始。 如果_IRowCount_为负数， **QueryRows**通过向后移动指定的行数重置的起始点。 光标重置之后，将向顺序读取行。 
  
_LppRows_参数指向的[SRowSet](srowset.md)结构中作为**cRows**成员指示返回的行数。 如果返回零行： 
  
- 光标已被置于表的开始和_IRowCount_的值为负数。 -或者- 
    
- 光标已位于表末尾和_IRowCount_的值为正数。 
    
列数和它们的顺序是相同的每个行。 如果属性不存在的行或读取属性时出错，行中的属性的**SPropValue**结构包含以下值： 
  
- 属性类型**ulPropTag**成员中 PT_ERROR。 
    
- **值**成员的 MAPI_E_NOT_FOUND。 
    
用于_lppRows_参数指向在行集中的[SPropValue](spropvalue.md)结构内存必须单独分配和释放对于每个行。 使用[MAPIFreeBuffer](mapifreebuffer.md)以释放属性值结构并释放行设置。 时对**QueryRows**的调用返回零，但是，指示的开头或结尾的表中，仅本身**SRowSet**结构需要释放。 有关如何分配和释放内存**SRowSet**结构中的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。
  
返回的行和所返回的顺序取决于成功的呼叫进行了[IMAPITable::Restrict](imapitable-restrict.md)和[IMAPITable::SortTable](imapitable-sorttable.md)。 **限制**筛选器行从视图中，导致**QueryRows**返回符合条件限制中指定的行。 **SortTable**建立一种标准，或者分类影响**QueryRows**所返回的行的顺序排序次序。 在传递给**SortTable** [SSortOrderSet](ssortorderset.md)结构中指定的顺序是返回的行。
  
对于每个行返回列和所返回的顺序取决于成功调用对进行了[IMAPITable::SetColumns](imapitable-setcolumns.md)。 **SetColumns**建立一列中，指定要包括在表和在其中他们应包含的顺序中的列的属性。 如果已**SetColumns**呼叫，每一行和这些列的顺序中的特定列将匹配设置调用中指定的列。 如果已没有**SetColumns**呼叫，表返回其默认列集。 
  
如果已尽可能无这些呼叫， **QueryRows**将返回的所有行表中。 每个行包含默认列中默认顺序设置。 
  
当建立[IMAPITable::SetColumns](imapitable-setcolumns.md)将调用的列集包括设为 PR_NULL 列时，在行集中返回_lppRows_ [SPropValue](spropvalue.md)数组将包含空插槽。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

您可以允许呼叫者可以请求列设置中包含不受支持的列。 当发生这种情况时，PT_ERROR 置于属性类型的部分属性标记和 MAPI_E_NOT_FOUND 中不受支持的列的属性值。 
  
视为请求，而不是必需的行数。 您可以任意位置从返回零行中是否存在任何行查询，到请求的数目的方向。 
  
返回只有该用户将看到行分类的表视图，从请求时允许呼叫者有关数据的范围进行有效假设，避免额外的工作的行。 
  
## <a name="notes-to-callers"></a>给调用方的说明

通常您将结尾任意具有_lRowCount_参数中指定数量的行。 但是，当内存或实现的限制是问题或操作提前达到的开始或表末尾， **QueryRows**将返回较少比所请求的行。 
  
如果**QueryRows**返回 MAPI_E_BUSY，调用[IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md)方法，并异步操作完成后重试**QueryRows**调用。 
  
当调用**QueryRows**，请注意，所需的异步通知的时间可能会导致，您可以返回从**QueryRows**不准确地表示基础数据行集。 例如，调用**QueryRows**到某个文件夹的内容表以下删除一条消息，但之前收到的相应通知会导致要返回的行中的已删除的行设置。 总是等待通知来更新用户的数据视图之前完成。 
  
有关从表中检索行的详细信息，请参阅[从表格行检索数据](retrieving-data-from-table-rows.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |DwThreadFuncLoadTable  <br/> |MFCMAPI 使用**IMAPITable::QueryRows**方法检索要加载到视图的表中的行。  <br/> |
   
## <a name="see-also"></a>另请参阅



[ADRENTRY](adrentry.md)
  
[FreeProws](freeprows.md)
  
[HrQueryAllRows](hrqueryallrows.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SRow](srow.md)
  
[SRowSet](srowset.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

