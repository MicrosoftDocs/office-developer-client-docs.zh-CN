---
title: IMAPITableSortTable
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.SortTable
api_type:
- COM
ms.assetid: ff5f78ac-06cf-46fb-93da-5f4a3a5d1b22
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f16ba9164d55fdb7bd688d4068f99dc4407e5413
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432364"
---
# <a name="imapitablesorttable"></a>IMAPITable::SortTable

**适用于**：Outlook 2013 | Outlook 2016 
  
**IMAPITable：：SortTable** 方法根据排序条件对表的行进行排序。 
  
```cpp
HRESULT SortTable(
LPSSortOrderSet lpSortCriteria,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

_lpSortCriteria_
  
> [in]指向包含要 [应用排序条件的 SSortOrderSet](ssortorderset.md) 结构的指针。 传递包含 **零列的 SSortOrderSet** 结构指示无需按任何特定顺序对表进行排序。 
    
_ulFlags_
  
> [in]控制 **IMAPITable：：SortTable 操作计时的标志的位** 掩码。 可以设置以下标志： 
    
TBL_ASYNC 
  
> 异步启动操作，在操作完成之前返回。
    
TBL_BATCH 
  
> 延迟排序的完成，直到需要表中的数据。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 排序操作成功。
    
MAPI_E_BUSY 
  
> 正在进行另一个阻止排序操作启动的操作。 应允许完成或停止进行中的操作。
    
MAPI_E_NO_SUPPORT 
  
> 该表不支持所请求的排序类型。
    
MAPI_E_TOO_COMPLEX 
  
> 表无法执行该操作，因为  _lpSortCriteria_ 参数指向的特定排序条件过于复杂。 **SortTable** 可以在MAPI_E_TOO_COMPLEX返回值。 
    
   - 为实现无法排序的属性列请求排序操作。
    
   - 实现不支持 **SSortOrderSet** 结构的 **ulOrder** 成员中请求的排序顺序。 
    
   - **SSortOrderSet** 中的 **cSorts** 成员中指定的要排序的列数大于实现可以处理的数量。
    
   - 请求排序操作，如 **SSortOrderSet** 中的属性标记所指示，它基于不在可用集或活动集内的属性，并且实现不支持对不在可用集内的属性进行排序。
    
   - 一个属性按排序顺序集多次指定，如同一属性标记的多个实例所指示，并且实现无法执行此类排序操作。
    
   - 基于多值属性列的排序操作是使用 MVI_FLAG 并且实现不支持对多值属性进行排序。 
    
   - **SSortOrderSet** 中属性的属性标记指定实现不支持的属性或类型。 
    
   - 除了从 **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性向前浏览表的排序操作外，只为支持这种类型的排序的附件表指定排序操作。
    
## <a name="remarks"></a>备注

**IMAPITable：：SortTable** 方法对表视图中的行进行排序。 有些表支持对各种排序键列的标准排序和分类排序，而其他表的支持则更加有限。 通讯簿提供程序通常不支持表排序。 邮件存储提供程序通常支持按以下程度进行排序：当完整表在表中排序时，它们保持 (排序时) 排序。 
  
某些表允许对任意表列进行排序。 其他表不能;表视图中未包含的列不受 **SortTable** 调用的影响。 某些表要求仅对表的当前列集的列构建排序键。 
  
当表无法完成排序MAPI_E_NO_SUPPORT，MAPI_E_TOO_COMPLEX **返回 SortTable** 中的一个或多个值。 此外，不保证存储提供程序遵守为层次结构表指定的排序顺序。 
  
当 _lpSortCriteria_ 参数指向 [的 SSortOrderSet](ssortorderset.md)结构中有零列时，表将返回当前列集。 可以通过调用表的 [IMAPITable：：QuerySortOrder](imapitable-querysortorder.md) 方法检索当前的排序顺序。 
  
表格的所有书签都失效，应在调用 **SortTable** 时删除，并且指示当前光标位置的 BOOKMARK_CURRENT 书签应设置为表格的开头。 
  
如果要对包含多值属性的列进行排序，而未设置 MVI_FLAG 标志，则列的值将被视为完全有序的元组。 两个多值列的比较将按顺序比较列元素，报告第一个不相等的列的关系，并且仅在进行比较的列包含相同值时返回相等值。 如果一列的值数少于另一列的值，则报告的关系为空值与另一个值的关系。
  
## <a name="notes-to-callers"></a>给调用方的说明

**SortTable** 将同步运行，除非您设置了其中一个标志。 如果设置了该 **TBL_BATCH，SortTable** 将推迟排序操作，除非您请求数据。 如果 **TBL_ASYNC，SortTable** 将异步运行，并且可能会在完成操作之前返回。 
  
如果必须立即排序，请调用 [IMAPITable：：Abort](imapitable-abort.md) 方法来停止进行中的异步操作。 如果 **SortTable** 由于表上的一个或多个异步操作正在进行而无法继续，它将返回 MAPI_E_BUSY。 
  
为获得最佳性能，在调用 **SortTable** 执行排序之前，请调用 **SetColumns** 自定义表的列集和 **Restrict** 以限制表中的行数。 
  
每当 **SortTable** 失败时，在失败之前生效的排序顺序仍然有效。 
  
## <a name="see-also"></a>另请参阅

- [IMAPITable::Abort](imapitable-abort.md)
- [IMAPITable::GetRowCount](imapitable-getrowcount.md)
- [IMAPITable::QueryColumns](imapitable-querycolumns.md)
- [IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
- [IMAPITable::SetColumns](imapitable-setcolumns.md)
- [SSortOrderSet](ssortorderset.md)
- [IMAPITable : IUnknown](imapitableiunknown.md)

