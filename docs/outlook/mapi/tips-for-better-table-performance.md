---
title: 更好的表性能的提示
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ac82f7e8-6453-4b4f-8223-3c23d09ca4c6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2b14c4fe8cbbadb2ccdd6a2f7870a07d2f96a3c9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778976"
---
# <a name="tips-for-better-table-performance"></a>更好的表性能的提示
  
**适用于**： Outlook 
  
因为许多表操作可以非常耗时并且没有方法以指示进度，非常有用用于提高性能的以下技术：
  
- **进行[IMAPITable: IUnknown](imapitableiunknown.md)调用以正确的顺序**
    
   客户端和服务提供商可以使用表中的各种方式。 它们可以打开的表格并检索所有使用默认列集的行的数据排序顺序。 此外，他们可以通过更改列集，更改排序次序，或建立缩小表的范围限制修改表的此默认视图。 要检索任何数据之前执行一个或多个这些操作的表用户应执行这些顺序如下：
    
    1. 定义与[IMAPITable::SetColumns](imapitable-setcolumns.md)设置的列。
        
    2. 建立与[IMAPITable::Restrict](imapitable-restrict.md)限制。
        
    3. 定义与[IMAPITable::SortTable](imapitable-sorttable.md)排序顺序。
    
    按此顺序执行这些任务限制的行和列将进行排序，从而提高性能的数量。
    
- **延迟尽可能使用 TBL_BATCH 标志操作**
    
    设置 TBL\_方法的批处理标志允许表实施者可以在任意一上收集执行之前的多个呼叫。 而不是使可能很多呼叫到远程服务器;表实施可以先创建一个，一次执行所有操作。 在需要时才不计算操作的结果。 
    
    例如，当客户端调用[IMAPITable::Restrict](imapitable-restrict.md) TBL 指定限制\_批处理标志设置限制不必进入效果，直到客户端调用[IMAPITable::QueryRows](imapitable-queryrows.md)检索数据。 这样，若要合并的两个呼叫到一个工作表实施。 表用户充分利用 TBL 的\_可能更复杂的错误处理在这些情况下应注意批次标志。 
    
    因为处理从延迟的请求操作错误是类似于处理错误时 MAPI\_设置 DEFERRED_ERRORS 标志、 详细信息，请参阅[推迟 MAPI 错误](deferring-mapi-errors.md)。 
    
- **保留缓存的常用属性**
    
    服务提供商实现表可以减少缓存副本的常用的对象属性创建视图所需的时间。 必须重建视图中无需每次都从对象中检索它们的内存保存保留一份这些属性。
    
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

