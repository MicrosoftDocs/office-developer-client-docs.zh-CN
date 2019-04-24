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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328817"
---
# <a name="imapitablesetcolumns"></a>IMAPITable::SetColumns

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义在表中显示为列的特定属性和属性的顺序。
  
```cpp
HRESULT SetColumns(
LPSPropTagArray lpPropTagArray,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpPropTagArray_
  
> 实时指向一个属性标记数组的指针, 这些标记用于标识要作为表中的列包含的属性。 可以将每个标记的属性类型部分设置为有效的类型或**PR_NULL** , 以便为后续添加保留空间。 _lpPropTagArray_参数不能设置为 NULL;每个表必须至少有一列。 
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制对**SetColumns**的异步调用的返回, 例如, 在通知中使用**SetColumns**时。 可以设置以下标志: 
    
TBL_ASYNC 
  
> 请求以异步方式执行列设置操作, 从而导致**SetColumns**在操作完全完成之前可能会返回。 
    
TBL_BATCH 
  
> 允许表将列设置操作延期, 直到实际需要数据。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 列设置操作成功。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作, 以防止启动列设置操作。 应允许正在进行的操作完成, 或者应已停止。
    
## <a name="remarks"></a>注解

表的列集是组成表中各行的列的一组属性。 为每种类型的表设置了默认列。 默认列集由表实施者自动包括的属性组成。 表用户可以通过调用**IMAPITable:: SetColumns**方法来更改此默认集。 如果表实施者支持将列删除或列的顺序发生更改, 则用户可以请求将其他列添加到默认集。 **SetColumns**指定每行返回的列和行中这些列的顺序。 
  
仅在随后调用以检索表的数据之后, **SetColumns**操作的成功才会变得明显。 然后, 报告任何错误。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

某些提供程序允许**SetColumns**调用仅对表视图的可用列中的表列进行排序。 其他提供程序允许**SetColumns**调用对表中的所有列进行排序, 包括那些包含不在原始列集中的属性。 
  
当 TBL_BATCH 设置为异步操作时, 提供程序应返回 PT_ERROR 的属性类型和不受支持的列的属性值为 NULL。
  
您无需响应 TBL_ASYNC 标志, 请求操作为异步操作。 如果不支持异步列集定义, 请同步执行该操作。 如果您可以支持 TBL_ASYNC 标志, 而另一个异步操作仍在进行中, 则返回 MAPI_E_BUSY。 否则, 无论是否支持属性标记数组中包含的所有属性, 都将返回 S_OK。 由于不受支持的属性而产生的错误应从检索数据的**IMAPITable**方法 (如**QueryRows**) 中返回。 
  
不会为通过调用**限制**而隐藏的表行生成通知。 
  
发送表通知时, [TABLE_NOTIFICATION](table_notification.md)结构的**行**成员中的属性顺序和由最近的**SetColumns**调用指定的顺序必须与通知请求的时间相同。已发送。 
  
另一个标志 TBL_BATCH, 允许呼叫者指定表实施者可以延迟评估操作结果, 直到更晚的时间。 只要有可能, 呼叫者都应设置此标志, 因为批处理操作可提高性能。
  
通常, 调用方可以在检索到的行中保留一些列, 以便日后添加值。 调用方通过在传递给**SetColumns**的属性标记数组中的所需位置放置**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 来实现此目的。然后, 该表将在使用**QueryRows**检索的所有行中的这些位置上传递 back **PR_NULL** 。
  
## <a name="notes-to-callers"></a>给调用方的说明

为_lpPropTagArray_参数生成属性标记数组时, 请按照您希望列在表视图中显示的顺序对标记进行排序。 
  
通过将多值实例标志 (或 MVI_FLAG 常量) 应用于属性标记, 可以指定要包含在列集中的多值属性。 通过将属性的单值版本的属性标记作为参数传递给 MVI_PROP 宏, 可以设置此标志, 如下所示:
  
```
MVI_PROP(ulPropTag)

```

MVI_PROP 宏将设置属性的 MVI_FLAG, 并将标记转换为多值标记。 如果您错误地尝试在单值属性上调用 MVI_PROP, MAPI 将忽略该调用并保持属性标记不变。 
  
您可以包含设置为**PR_NULL**的属性标记数组中的属性标记, 以在列集中保留空间。 通过保留空间, 可以将添加到列集, 而无需分配新的属性标记数组。 
  
当您对**SetColumns**的调用导致对表的列的顺序的更改, 并且其中的一个或多个列表示多值属性时, 表中的行数可能会增加。 如果出现这种情况, 将丢弃表的所有书签。 有关多值列对表的影响的详细信息, 请参阅[使用多值列](working-with-multivalued-columns.md)。
  
默认情况下, 设置列是同步操作。 但是, 可以通过设置 TBL_BATCH 标志, 允许表延迟操作, 直到需要数据时才使用。 设置此标志可以提高性能。 另一个标志 TBL_ASYNC, 使操作成为异步操作, 允许**SetColumns**在操作完成前返回。 若要确定完成发生的时间, 请调用[IMAPITable:: GetStatus](imapitable-getstatus.md)。
  
如果对**SetColumns**的调用返回 MAPI_E_BUSY, 表明另一个操作正在阻止您的操作启动, 则可以调用[IMAPITable:: Abort](imapitable-abort.md)停止正在进行的操作。 
  
您还可以调用[HrAddColumnsEx](hraddcolumnsex.md)更改列集。 **HrAddColumnsEx**和**IMAPITable:: SetColumns**之间的差异在于, **HrAddColumnsEx**的灵活性较低;它只能添加列。 其他列位于列集的开头;所有现有列都显示在这些列之后。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl  <br/> |CContentsTableListCtrl::D osetcolumns  <br/> |MFCMAPI 使用**IMAPITable:: SetColumns**方法为表设置所需的列。  <br/> |
   
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

