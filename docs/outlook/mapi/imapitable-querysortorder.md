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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 48ca692779fb53cab386d8a18b5f0a50e11d531c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569433"
---
# <a name="imapitablequerysortorder"></a>IMAPITable::QuerySortOrder

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
检索当前表格排序顺序。
  
```cpp
HRESULT QuerySortOrder(
LPSSortOrderSet FAR * lppSortCriteria
);
```

## <a name="parameters"></a>参数

 _lppSortCriteria_
  
> [输出]为存放当前的排序顺序[SSortOrderSet](ssortorderset.md)结构指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回当前的排序顺序。
    
MAPI_E_BUSY 
  
> 阻止排序顺序检索操作启动的正在进行中是另一个操作。 应允许正在进行的操作完成或应停止。
    
## <a name="remarks"></a>注解

**IMAPITable::QuerySortOrder**方法检索当前表格排序顺序。 [SSortOrderSet](ssortorderset.md)结构描述都排序次序。 
  
- **SSortOrderSet**结构的**cSorts**成员可以设置为零，如果： 
    
- 表未排序。
    
- 没有任何信息对表进行排序。
    
- **SSortOrderSet**结构不适合描述的排序次序。 
    
## <a name="notes-to-implementers"></a>针对实施者的注释

如果具有包含零个列的排序关键字**SSortOrderSet**结构进行[IMAPITable::SortTable](imapitable-sorttable.md)方法调用时，删除当前的排序顺序，并应用默认的顺序，如果有。 中到**QuerySortOrder**的后续呼叫，您可以选择是否返回零个或多个列的排序关键字。 您可以返回多于存在视图中的列数。
  
有关排序的详细信息，请参阅[排序和分类](sorting-and-categorization.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPITable::SortTable](imapitable-sorttable.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SSortOrderSet](ssortorderset.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)

