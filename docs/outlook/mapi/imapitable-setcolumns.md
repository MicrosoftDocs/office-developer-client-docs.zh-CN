---
title: IMAPITableSetColumns
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.SetColumns
api_type:
- COM
ms.assetid: 9a39cf8d-df0f-493c-b272-f15c65b3f15e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 897330feb216dbc3ab143378977c77141cf488f0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416347"
---
# <a name="imapitablesetcolumns"></a>IMAPITable::SetColumns

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义要作为表格中的列显示的属性的特定属性和顺序。
  
```cpp
HRESULT SetColumns(
LPSPropTagArray lpPropTagArray,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpPropTagArray_
  
> [in]指向属性标记数组的指针，用于标识要作为表中的列包含的属性。 每个标记的属性类型部分可以设置为有效类型，也可以设置为PR_NULL保留空间以用于后续添加。 _lpPropTagArray_ 参数不能设置为 NULL;每个表都必须至少有一列。 
    
 _ulFlags_
  
> [in]控制对 **SetColumns** 的异步调用返回的标志的位掩码，例如，在通知中使用 **SetColumns** 时。 可以设置以下标志： 
    
TBL_ASYNC 
  
> 请求异步执行列设置操作，导致 **SetColumns** 在操作完全完成之前可能返回。 
    
TBL_BATCH 
  
> 允许表推迟列设置操作，直到实际需要数据。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 列设置操作成功。
    
MAPI_E_BUSY 
  
> 另一个操作正在进行中，该操作阻止列设置操作启动。 应允许完成或停止进行中的操作。
    
## <a name="remarks"></a>备注

表格的列集是组成表格中行的列的属性组。 每种类型的表都有一个默认列集。 默认列集由表实现程序自动包含的属性所决定。 表用户可以通过调用 **IMAPITable：：SetColumns** 方法来更改此默认设置。 如果表实现程序支持删除其他列，或者更改列的顺序，则它们可以请求将其他列添加到默认集。 **SetColumns** 指定每行返回的列以及这些列在行中的顺序。 
  
只有在执行后续调用以检索表数据后 **，SetColumns** 操作才明显成功。 然后报告任何错误。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

某些提供程序允许 **SetColumns** 调用仅对表视图的可用列的表列进行排序。 其他提供程序允许 **SetColumns** 调用来排序所有表列，包括那些包含原始列集外的属性的列。 
  
当TBL_BATCH异步操作时，提供程序应返回属性类型的值PT_ERROR不支持的列的属性值为 NULL。
  
你无需响应请求TBL_ASYNC异步的异步标记。 如果不支持异步列集定义，请同步执行此操作。 如果可以支持该TBL_ASYNC，并且另一个异步操作仍在进行中，请返回MAPI_E_BUSY。 否则，S_OK返回值，而不管是否支持属性标记数组中包含的所有属性。 由不受支持的属性导致的错误应从检索数据的 **IMAPITable** 方法返回，如 **QueryRows**。 
  
不要为通过调用 Restrict 从视图中隐藏的表行 **生成通知**。 
  
发送表通知时 [，TABLE_NOTIFICATION](table_notification.md)结构的行成员中的属性顺序和最近的 **SetColumns** 调用指定的顺序必须与发送通知请求的时间相同。 
  
另一个标志（TBL_BATCH）允许调用方指定表实施者可以将计算操作结果延迟到稍后时间。 如果可能，调用方应设置此标志，因为批处理操作可提高性能。
  
调用方通常可以方便地在检索到的行集内保留一些列，以用于稍后添加的值。 调用方通过将 [PidTagNull PR_NULL (PidTagNull](pidtagnull-canonical-property.md)) 传递到 **SetColumns** 的属性标记数组中的所需位置来达到此目的。 然后，该表将 **传递PR_NULL** **QueryRows** 检索到的所有行中这些位置的位置。
  
## <a name="notes-to-callers"></a>给调用方的说明

为  _lpPropTagArray_ 参数构建属性标记数组时，按希望列在表视图中显示的顺序对标记进行排序。 
  
通过向属性标记应用多值实例标志或MVI_FLAG，可以指定列集中包含的多值属性。 通过将单值版本的属性的属性标记作为参数传递给 MVI_PROP宏，以设置此标志，如下所示：
  
```
MVI_PROP(ulPropTag)

```

The MVI_PROP macro will set MVI_FLAG for the property， turning the tag into a multivalued tag. 如果错误地尝试对单值MVI_PROP调用属性，MAPI 将忽略该调用，并保留属性标记不变。 
  
可以在属性标记数组中添加 **PR_NULL** 属性标记，以在列集内保留空间。 保留空间允许您添加到列集，而无需分配新的属性标记数组。 
  
如果对 **SetColumns** 的调用导致表的列顺序发生变化，并且其中一个或多个列代表多值属性，则表格中的行数可能会增加。 如果发生这种情况，将放弃表格的所有书签。 有关多值列如何影响表的信息，请参阅使用 [多值列](working-with-multivalued-columns.md)。
  
默认情况下，设置列是同步操作。 但是，可以通过设置数据标记来允许表将操作推迟到需要TBL_BATCH的时间。 设置此标志可提高性能。 另一个TBL_ASYNC标记使操作异步，从而允许 **SetColumns** 在操作完成之前返回。 若要确定完成时间，请调用 [IMAPITable：：GetStatus](imapitable-getstatus.md)。
  
如果对 **SetColumns** 的调用返回 MAPI_E_BUSY，指示另一个操作阻止了操作启动，您可以调用 [IMAPITable：：Abort](imapitable-abort.md) 以停止进行中的操作。 
  
还可以调用 [HrAddColumnsEx](hraddcolumnsex.md) 更改列集。 **HrAddColumnsEx** 和 **IMAPITable：：SetColumns** 之间的区别在于 **HrAddColumnsEx** 灵活性较低;它只能添加列。 其他列放置在列集的开头;所有现有列都显示在这些列之后。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl：:D oSetColumns  <br/> |MFCMAPI 使用 **IMAPITable：：SetColumns** 方法设置表的所需列。  <br/> |
   
## <a name="see-also"></a>另请参阅



[HrQueryAllRows](hrqueryallrows.md)
  
[IMAPITable::Abort](imapitable-abort.md)
  
[IMAPITable::GetRowCount](imapitable-getrowcount.md)
  
[IMAPITable::QueryColumns](imapitable-querycolumns.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::Restrict](imapitable-restrict.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[SPropTagArray](sproptagarray.md)
  
[SPropValue](spropvalue.md)
  
[SRowSet](srowset.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

