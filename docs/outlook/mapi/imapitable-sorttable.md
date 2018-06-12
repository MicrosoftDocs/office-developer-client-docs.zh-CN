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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 46a87a6eb5c80244c04ae6257cd4441b8797ba36
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775726"
---
# <a name="imapitablesorttable"></a>IMAPITable::SortTable

**适用于**： Outlook 
  
**IMAPITable::SortTable**方法对行进行排序的表中，具体取决于排序条件。 
  
```cpp
HRESULT SortTable(
LPSSortOrderSet lpSortCriteria,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

_lpSortCriteria_
  
> [in]指向[SSortOrderSet](ssortorderset.md)结构，其中包含要应用的排序条件。 传递**SSortOrderSet**结构，其中包含零个列指示表不需要任何特定顺序排序。 
    
_ulFlags_
  
> [in]位掩码的标志，控制**IMAPITable::SortTable**操作的时间。 可以设置以下标志： 
    
TBL_ASYNC 
  
> 异步启动操作并返回才能完成此操作。
    
TBL_BATCH 
  
> 延迟排序完成，直到表中的数据，则需要。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 排序操作已成功。
    
MAPI_E_BUSY 
  
> 正在进行中，可以防止启动排序操作是另一个操作。 应允许正在进行的操作完成或应停止。
    
MAPI_E_NO_SUPPORT 
  
> 表不支持的排序请求的类型。
    
MAPI_E_TOO_COMPLEX 
  
> 表无法执行操作，因为太复杂_lpSortCriteria_参数指向的特定的排序条件。 **SortTable**可以在下列情况下返回 MAPI_E_TOO_COMPLEX。 
    
   - 排序操作被请求属性列实现不能进行排序。
    
   - 实现不支持在**SSortOrderSet**结构的**ulOrder**成员中请求的排序次序。 
    
   - 要进行排序的列数中**SSortOrderSet** **cSorts**成员指定，大于所实现可处理。
    
   - 请求排序操作，由**SSortOrderSet**，基于不在可用的或活动集中属性中的属性标记和实现不支持排序不在可用集合的属性。
    
   - 一个属性是多次集合中指定排序顺序，由多个实例的相同属性标记，并实现无法执行排序操作。
    
   - 基于多值的属性列排序操作请求使用 MVI_FLAG 并实现不支持多值属性排序。 
    
   - 属性标记中**SSortOrderSet**为属性指定的属性或实现不支持的类型。 
    
   - 仅支持这种类型的排序附件表指定排序操作以外从头到尾转接**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性中的表。
    
## <a name="remarks"></a>备注

**IMAPITable::SortTable**方法在表视图中对行进行排序。 某些表格中支持标准和分类键列的排序各种上排序，而其他表在支持更多限制。 通讯簿提供程序通常不支持表排序。 消息存储提供程序通常支持的范围内它们保留文件夹的完整表格 （无限制） 进行排序时结果的排序顺序排序。 
  
某些表格中允许要完成的任何表格列进行排序。 其他表不;不包含在表视图中的列不受**SortTable**呼叫。 某些表格中需要排序关键字构建仅与表的当前列组中的列。 
  
表可以返回 MAPI_E_NO_SUPPORT 或 MAPI_E_TOO_COMPLEX 从**SortTable**它不能完成排序操作时。 此外，存储提供程序不能保证服从设置指定的层次结构表的排序次序。 
  
当_lpSortCriteria_参数指向[SSortOrderSet](ssortorderset.md)结构中存在零列时，表返回当前的列集。 可以通过调用表的[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法来检索当前的排序顺序。 
  
表的所有书签将无效，并应删除时调用**SortTable**不进行，并且 BOOKMARK_CURRENT 书签，该值指示当前光标位置，应设置为表的开头。 
  
如果在包含一个多值的属性没有设置 MVI_FLAG 标志的列上排序，列的值将被视为完全有序元组。 两个多值列的比较比较中报告的第一个不相等中的列的关系的顺序的列元素，并返回相等，才进行比较的列包含相同的顺序相同的值。 如果一个列具有比其他值少，报告的关系是 null 值为其他值。
  
## <a name="notes-to-callers"></a>给调用方的说明

除非将其中一个标志设置**SortTable**进行同步操作。 如果设置 TBL_BATCH 标志， **SortTable**推迟排序操作，除非您请求的数据。 如果设置了 TBL_ASYNC 标志， **SortTable**操作以异步方式，可能返回之前完成操作。 
  
调用[IMAPITable::Abort](imapitable-abort.md)方法以停止正在进行的异步操作，如果立即必须进行排序。 如果**SortTable**无法继续，因为一个或多个表的异步操作正在进行，则将返回 MAPI_E_BUSY。 
  
为了获得最佳性能，调用**SetColumns**自定义表的列组并**限制**以限制的表中的行数之前调用**SortTable**执行排序。 
  
只要**SortTable**失败，已起作用之前失败的排序顺序所做的更改。 
  
## <a name="see-also"></a>另请参阅

- [IMAPITable::Abort](imapitable-abort.md)
- [IMAPITable::GetRowCount](imapitable-getrowcount.md)
- [IMAPITable::QueryColumns](imapitable-querycolumns.md)
- [IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
- [IMAPITable::SetColumns](imapitable-setcolumns.md)
- [SSortOrderSet](ssortorderset.md)
- [IMAPITable: IUnknown](imapitableiunknown.md)

