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
  
从当前游标位置开始, 返回表中的一个或多个行。
  
```cpp
HRESULT QueryRows(
LONG lRowCount,
ULONG ulFlags,
LPSRowSet FAR * lppRows
);
```

## <a name="parameters"></a>参数

 _lRowCount_
  
> 实时要返回的最大行数。
    
 _ulFlags_
  
> 实时控制如何返回行的标志的位掩码。 可以设置以下标志:
    
TBL_NOADVANCE 
  
> 防止因行检索而导致光标不前移。 如果设置了 TBL_NOADVANCE 标志, 则游标指向返回的第一行。 如果未设置 TBL_NOADVANCE 标志, 则游标指向返回的最后一行后面的行。
    
 _lppRows_
  
> 排除指向包含表行的[SRowSet](srowset.md)结构的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回行。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作, 以阻止行检索操作启动。 应允许正在进行的操作完成, 或者应已停止。
    
MAPI_E_INVALID_PARAMETER 
  
> 将_IRowCount_参数设置为零。 
    
## <a name="remarks"></a>说明

**IMAPITable:: QueryRows**方法从表中获取一个或多个数据行。 _IRowCount_参数的值影响检索的起始点。 如果_IRowCount_为正数, 则从当前位置开始沿正向方向读取行。 如果_IRowCount_为负值, **QueryRows**将通过向后移动指定的行数来重置起始点。 重置游标后, 将按正向顺序读取行。 
  
由_lppRows_参数指向的[SRowSet](srowset.md)结构中的**cRows**成员指示返回的行数。 如果返回零行: 
  
- 游标已经定位在表的开头, _IRowCount_的值为负值。 和 
    
- 游标已经定位在表的末尾, _IRowCount_的值是正数。 
    
列数及其排序对于每一行都是相同的。 如果某一行的属性不存在, 或者在读取属性时出现错误, 则该行中的该属性的**SPropValue**结构包含以下值: 
  
- **ulPropTag**成员中的属性类型的 PT_ERROR。 
    
- MAPI_E_NOT_FOUND 为**Value**成员。 
    
为_lppRows_参数所指向的行集中的[SPropValue](spropvalue.md)结构使用的内存必须为每个行单独分配和释放。 使用[MAPIFreeBuffer](mapifreebuffer.md)释放属性值结构并释放行集。 但是, 当对**QueryRows**的调用返回0时, 指示表的开头或结尾, 只有**SRowSet**结构本身需要释放。 有关如何在**SRowSet**结构中分配和释放内存的详细信息, 请参阅[管理内存中的 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。
  
返回的行以及返回的顺序取决于是否对[IMAPITable:: Restrict](imapitable-restrict.md)和[imapitable:: SortTable](imapitable-sorttable.md)进行了成功的调用。 **限制**筛选视图中的行, 从而导致**QueryRows**仅返回与限制中指定的条件匹配的行。 **SortTable**建立标准的或已分类的排序顺序, 从而影响**QueryRows**返回的行序列。 返回的行的顺序与传递给**SortTable**的[SSortOrderSet](ssortorderset.md)结构中指定的顺序相同。
  
为每个行返回的列及其返回的顺序取决于是否对[IMAPITable:: SetColumns](imapitable-setcolumns.md)成功进行了调用。 **SetColumns**建立列集, 指定要包含在表的列中的属性以及应包含的顺序。 如果进行了**SetColumns**调用, 则每行中的特定列和这些列的顺序与调用中指定的列集相匹配。 如果未进行任何**SetColumns**调用, 则该表将返回其默认列集。 
  
如果未进行这些调用, 则**QueryRows**将返回表中的所有行。 每行都包含默认的默认列集。 
  
当在对[IMAPITable:: SetColumns](imapitable-setcolumns.md)的调用中建立的列集包含设置为 PR_NULL 的列时, _lppRows_中返回的行集内的[SPropValue](spropvalue.md)数组将包含空槽。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您可以允许呼叫者请求在列集中包含不受支持的列。 发生这种情况时, 请将 PT_ERROR 置于属性标记的属性类型部分, 并在属性值中为不受支持的列键入 MAPI_E_NOT_FOUND。 
  
将行数视为请求而不是要求。 如果在查询的方向上没有行, 则可以从零行返回到请求的数量。 
  
仅返回在分类表视图中请求行时用户将看到的行, 从而允许调用方对数据范围做出有效假设并避免额外的工作。 
  
## <a name="notes-to-callers"></a>给调用方的说明

通常情况下, 您最终会拥有在_lRowCount_参数中指定的多个行。 但是, 当内存或实现限制出现问题, 或者操作在提前到达表的开头或结尾时, **QueryRows**将返回的行数少于请求的行数。 
  
如果**QueryRows**返回 MAPI_E_BUSY, 则调用[IMAPITable:: WaitForCompletion](imapitable-waitforcompletion.md)方法, 并在异步操作完成时重试对**QueryRows**的调用。 
  
调用**QueryRows**时, 请注意, 异步通知的计时可能会导致从**QueryRows**返回的行集不能准确表示基础数据。 例如, 在删除邮件之后但在收到相应通知之前, 对文件夹的内容表的**QueryRows**调用将导致删除的行在行集中返回。 始终等待通知在更新用户的数据视图之前到达。 
  
有关检索表中的行的详细信息, 请参阅[从表行检索数据](retrieving-data-from-table-rows.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl  <br/> |DwThreadFuncLoadTable  <br/> |MFCMAPI 使用**IMAPITable:: QueryRows**方法检索要加载到视图中的表中的行。  <br/> |
   
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

