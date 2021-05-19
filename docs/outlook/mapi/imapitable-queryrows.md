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
ms.openlocfilehash: 26d6ffe66a5e7749c9d8c4e5210e9f72de808932
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416291"
---
# <a name="imapitablequeryrows"></a>IMAPITable::QueryRows

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从表中的一行或多行，从当前光标位置开始。
  
```cpp
HRESULT QueryRows(
LONG lRowCount,
ULONG ulFlags,
LPSRowSet FAR * lppRows
);
```

## <a name="parameters"></a>参数

 _lRowCount_
  
> [in]要返回的最大行数。
    
 _ulFlags_
  
> [in]控制行返回方法的标志的位掩码。 可以设置以下标志：
    
TBL_NOADVANCE 
  
> 防止游标由于行检索而前进。 如果TBL_NOADVANCE，光标指向返回的第一行。 如果未TBL_NOADVANCE，则光标指向返回的最后一行后行。
    
 _lppRows_
  
> [out]指向指向保留表格 [行的 SRowSet](srowset.md) 结构的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回行。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作，以防止行检索操作启动。 应允许完成或停止进行中的操作。
    
MAPI_E_INVALID_PARAMETER 
  
> _IRowCount_ 参数设置为零。 
    
## <a name="remarks"></a>备注

**IMAPITable：：QueryRows** 方法从表中获取一行或多行数据。 _IRowCount_ 参数的值会影响检索的起始点。 如果  _IRowCount_ 为正数，则从当前位置开始以向前方向读取行。 如果  _IRowCount_ 为负数 **，QueryRows** 会通过向后移动指示的行数来重置起始点。 重置游标后，将按向前顺序读取行。 
  
**lppRows** 参数指向 [的 SRowSet](srowset.md)结构中 _cRows_ 成员指示返回的行数。 如果返回零行： 
  
- 光标已位于表的开头，  _并且 IRowCount_ 的值为负数。 -Or- 
    
- 光标已位于表的末尾，  _并且 IRowCount_ 的值为正。 
    
每行的列数及其排序相同。 如果行不存在属性或读取属性时出错，该行中属性的 **SPropValue** 结构将包含下列值： 
  
- PT_ERROR **ulPropTag** 成员中的属性类型。 
    
- MAPI_E_NOT_FOUND Value **成员** 。 
    
_lppRows_ 参数指向的行集内用于 [SPropValue](spropvalue.md)结构的内存必须单独分配，并针对每一行释放。 使用 [MAPIFreeBuffer](mapifreebuffer.md) 释放属性值结构并释放行集。 但是，当 **对 QueryRows** 的调用返回零时，指示表的开头或结尾，则仅 **需要释放 SRowSet** 结构本身。 若要详细了解如何在 **SRowSet** 结构中分配和释放内存，请参阅 [管理 ADRLIST 和 SRowSet 结构的内存](managing-memory-for-adrlist-and-srowset-structures.md)。
  
返回的行及其返回顺序取决于是否已成功调用 [IMAPITable：：Restrict](imapitable-restrict.md) 和 [IMAPITable：：SortTable](imapitable-sorttable.md)。 **限制** 视图中的筛选行，从而导致 **QueryRows** 仅返回与限制中指定的条件匹配的行。 **SortTable** 建立标准或分类的排序顺序，影响 **QueryRows** 返回的行的顺序。 返回的行按照传递给 SortTable [的 SSortOrderSet](ssortorderset.md) 结构中 **指定的顺序排列**。
  
每行返回的列及其返回顺序取决于是否已对 [IMAPITable：：SetColumns](imapitable-setcolumns.md)成功调用。 **SetColumns** 建立一个列集，指定要包含在表中的列中的属性以及这些属性的包含顺序。 如果 **已进行 SetColumns** 调用，则每行中的特定列以及这些列的顺序与调用中指定的列集匹配。 如果未进行 **SetColumns** 调用，则表将返回其默认列集。 
  
如果未进行这些调用 **，QueryRows** 将返回表中的所有行。 每行包含默认顺序的默认列集。 
  
当 [在 IMAPITable：：SetColumns](imapitable-setcolumns.md)的调用中建立的列集包含设置为 PR_NULL 的列时 _，lppRows_ 中返回的行集内的 [SPropValue](spropvalue.md)数组将包含空插槽。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您可以允许调用方请求将不受支持列包含在列集内。 当发生这种情况时，PT_ERROR属性标记的属性类型部分，MAPI_E_NOT_FOUND不受支持的列的属性值中。 
  
将行计数视为请求而不是要求。 如果查询方向没有行，可以从零行到请求的行数返回任意位置。 
  
仅返回在从分类表视图中请求行时用户将看到的行，从而允许调用方对数据范围做出有效的假设，并避免额外工作。 
  
## <a name="notes-to-callers"></a>给调用方的说明

通常，您最终将具有在  _lRowCount_ 参数中指定的行数。 但是，当内存或实现限制成为问题时，或者当操作提前到达表的开头或结尾时 **，QueryRows** 返回的行数将少于请求的行数。 
  
如果 **QueryRows** 返回 MAPI_E_BUSY，请调用 [IMAPITable：：WaitForCompletion](imapitable-waitforcompletion.md) 方法，在异步操作完成时重试 **对 QueryRows** 的调用。 
  
调用 **QueryRows** 时，请注意异步通知的计时可能会导致从 **QueryRows** 返回的行集无法准确表示基础数据。 例如，在删除邮件之后但在收到相应通知之前，对文件夹内容表的 **QueryRows** 调用将导致在行集内返回已删除的行。 在更新用户的数据视图之前，请始终等待通知到达。 
  
有关从表中检索行的信息，请参阅 [从表行检索数据](retrieving-data-from-table-rows.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |DwThreadFuncLoadTable  <br/> |MFCMAPI 使用 **IMAPITable：：QueryRows** 方法检索表中要加载到视图中的行。  <br/> |
   
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

