---
title: IMAPITableQuerySortOrder
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.QuerySortOrder
api_type:
- COM
ms.assetid: 7b4ca523-0703-417c-8586-c4324c200020
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 61991972fdf8674a9ffd2b790e26c7fa669df357
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407548"
---
# <a name="imapitablequerysortorder"></a>IMAPITable::QuerySortOrder

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索表的当前排序顺序。
  
```cpp
HRESULT QuerySortOrder(
LPSSortOrderSet FAR * lppSortCriteria
);
```

## <a name="parameters"></a>参数

 _lppSortCriteria_
  
> 排除指向包含当前排序顺序的[SSortOrderSet](ssortorderset.md)结构的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回当前排序顺序。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作, 以阻止排序顺序检索操作开始。 应允许正在进行的操作完成, 或者应已停止。
    
## <a name="remarks"></a>说明

**IMAPITable:: QuerySortOrder**方法检索表的当前排序顺序。 排序顺序是使用[SSortOrderSet](ssortorderset.md)结构进行描述的。 
  
- 如果为以下情况, **SSortOrderSet**结构的**cSorts**成员可设置为零: 
    
- 该表未排序。
    
- 不存在有关如何对表进行排序的信息。
    
- **SSortOrderSet**结构不适合用于描述排序顺序。 
    
## <a name="notes-to-implementers"></a>针对实现者的说明

如果使用在排序关键字中包含零列的**SSortOrderSet**结构对[IMAPITable:: SortTable](imapitable-sorttable.md)方法进行了调用, 则删除当前排序顺序并应用默认顺序 (如果有)。 在对**QuerySortOrder**的后续调用中, 可以选择是否返回零个或多个用于排序关键字的列。 您可以返回的列数多于当前视图中的列数。
  
有关排序的详细信息, 请参阅[排序和分类](sorting-and-categorization.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPITable::SortTable](imapitable-sorttable.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SSortOrderSet](ssortorderset.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

