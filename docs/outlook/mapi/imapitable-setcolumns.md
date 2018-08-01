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
ms.openlocfilehash: 9eeab1e1186aeb5a9b458facd59bd4cc155e8014
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775716"
---
# <a name="imapitablesetcolumns"></a>IMAPITable::SetColumns

  
  
**适用于**： Outlook 
  
定义的特定属性和属性的顺序显示为表中的列。
  
```cpp
HRESULT SetColumns(
LPSPropTagArray lpPropTagArray,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpPropTagArray_
  
> [in]指向属性标记标识属性必须包含作为表中的列的数组。 每个标记的属性类型部分可以设置为有效的类型或**PR_NULL**为后续增加保留空间。 不能_lpPropTagArray_参数设置为 NULL;每个表必须有至少一个列。 
    
 _ulFlags_
  
> [in]位掩码的标志控制的异步调用**SetColumns**，例如，在通知使用**SetColumns**时返回的。 可以设置以下标志： 
    
TBL_ASYNC 
  
> 列设置操作是请求执行异步导致**SetColumns**可能返回操作完全完成之前。 
    
TBL_BATCH 
  
> 允许该表推迟列设置操作，直到所实际需要的数据。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 列设置操作已成功。
    
MAPI_E_BUSY 
  
> 另一个操作正在进行阻止设置启动操作列中。 应允许正在进行的操作完成或应停止。
    
## <a name="remarks"></a>说明

表的列集是组的表中的行的列组成的属性。 没有为每种类型的表的默认列。 默认列集由属性表实施自动包含组成。 表的用户可以更改通过调用**IMAPITable::SetColumns**方法设置此默认值。 它们可以请求将其他列添加到默认的设置如果表实施支持其列被删除或更改列的顺序。 **SetColumns**与每个行的行中的这些列顺序指定返回的列。 
  
**SetColumns**操作成功很明显的仅后所做的后续调用来检索数据的表。 然后是报告了任何错误。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

某些提供程序允许**SetColumns**呼叫可仅属于表视图的可用列的表格列进行排序。 其他提供程序允许**SetColumns**呼叫进行排序所有的表格列，包括那些包含不在原始的列集的属性。 
  
当 TBL_BATCH 设置的异步操作时，提供程序应返回 PT_ERROR 属性类型，并且不受支持的列的空值的属性值。
  
不需要响应请求操作将异步 TBL_ASYNC 标志。 如果您不支持异步列集定义，同步执行操作。 您可以支持 TBL_ASYNC 标志，另一个异步操作仍在进度，返回 MAPI_E_BUSY。 否则，返回 S_OK 而不考虑支持所有属性标记数组中包括的属性。 应从的检索数据，如**QueryRows** **IMAPITable**方法返回错误生成不受支持的属性。 
  
不会生成通知处于隐藏状态的表格行从视图通过调用**限制**。 
  
时发送表通知、 [TABLE_NOTIFICATION](table_notification.md)结构中的**行**成员中的属性的顺序和顺序指定最近**SetColumns**调用必须相同截止通知请求的时间已发送。 
  
另一个标志，TBL_BATCH，允许呼叫者在指定表实施者可以将推迟评估直到以后操作的结果。 只要有可能，应将设置主叫方此标志，因为批处理的操作可以提高性能。
  
通常方便的呼叫者在保留中的值，以后添加检索的行集的某些列。 呼叫者在执行此操作在传递给**SetColumns**; 该属性标记数组中所需的位置设置一道**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md))表将传递回**PR_NULL**所有行中的这些位置检索与**QueryRows**然后。
  
## <a name="notes-to-callers"></a>给调用方的说明

构建_lpPropTagArray_参数属性标记数组时, 您想要在表视图中显示的列的顺序排序标记。 
  
您可以指定多值的属性包含设置通过将多值的实例标志或 MVI_FLAG 常量应用于属性标记列中。 设置此标志属性标记为单值属性的版本作为参数传递给 MVI_PROP 宏，如下所示：
  
```
MVI_PROP(ulPropTag)

```

MVI_PROP 宏将设置该属性，将转换的多值标记为标记 MVI_FLAG。 如果您错误地尝试调用 MVI_PROP 对单值属性，MAPI 将忽略呼叫并保持不变的属性标记。 
  
您可以包括属性设置为**PR_NULL**属性标记数组中保留空间列设置中的标记。 保留空间允许您添加到列设置而无需分配新的属性标记数组。 
  
**SetColumns**您调用使表的列的顺序发生的更改以及一个或多个列表示一个多值的属性时，可能要增加的表中的行数。 如果发生这种情况，将放弃所有表的书签。 详细了解如何多值的列会影响表，请参阅[使用多值列](working-with-multivalued-columns.md)。
  
设置列是默认情况下同步操作。 但是，您可以允许表，直到数据所需通过设置 TBL_BATCH 标志如次推迟操作。 将该标志设置可以提高性能。 另一个标志，TBL_ASYNC，使操作异步，允许**SetColumns**返回才能完成此操作。 若要确定完成发生时，请调用[IMAPITable::GetStatus](imapitable-getstatus.md)。
  
如果对**SetColumns**的调用返回 MAPI_E_BUSY，表示另一个操作阻止了您的操作启动，则可以呼叫[IMAPITable::Abort](imapitable-abort.md)停止正在进行的操作。 
  
您可以调用[HrAddColumnsEx](hraddcolumnsex.md)更改一列。 **HrAddColumnsEx**和**IMAPITable::SetColumns**之间的区别是**HrAddColumnsEx**是较低灵活;它只能添加列。 额外的列的位于列集; 的开头以下这些列将显示所有的现有列。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl::DoSetColumns  <br/> |MFCMAPI 使用**IMAPITable::SetColumns**方法设置所需的表的列。  <br/> |
   
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

