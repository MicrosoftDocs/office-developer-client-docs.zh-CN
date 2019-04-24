---
title: 表性能提升提示
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ac82f7e8-6453-4b4f-8223-3c23d09ca4c6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 82be33090a63f24c430007d9759045c365961f5d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327795"
---
# <a name="tips-for-better-table-performance"></a>表性能提升提示
  
**适用于**：Outlook 2013 | Outlook 2016 
  
由于许多表操作可能非常耗时且无法指示进度, 因此使用以下技术来提高性能有助于提高性能:
  
- **使[IMAPITable: IUnknown](imapitableiunknown.md)按正确的顺序呼叫**
    
   客户端和服务提供程序可以通过多种方式使用表。 他们可以打开表, 并使用默认列集和排序顺序检索所有行的数据。 此外, 他们还可以通过更改列集、更改排序顺序或建立限制以缩小表的范围来修改此表的默认视图。 要在检索任何数据之前执行这些操作中的一个或多个操作的表用户应按以下顺序执行这些操作:
    
    1. 使用[IMAPITable:: SetColumns](imapitable-setcolumns.md)定义列集。
        
    2. 使用[IMAPITable:: Restrict](imapitable-restrict.md)建立限制。
        
    3. 使用[IMAPITable:: SortTable](imapitable-sorttable.md)定义排序顺序。
    
    按此顺序执行这些任务将对要排序的行和列的数量进行限制, 从而提高性能。
    
- **如果可能, 请使用 TBL_BATCH 标志延迟操作**
    
    通过在方法\_上设置 TBL 批处理标志, 表实施者可以在操作任何一个调用之前收集多个调用。 而不是对远程服务器进行可能的多个调用; 而是表实施者可以创建一个, 一次执行所有操作。 在需要时才会评估操作的结果。 
    
    例如, 当客户端调用[imapitable:: Restrict](imapitable-restrict.md)来指定设置了 TBL\_批处理标志的限制时, 在客户端调用[IMAPITable:: QueryRows](imapitable-queryrows.md)检索数据时, 限制不会生效。 这使表实施者能够将两个调用的工作合并成一个。 利用 TBL\_批处理标志的表用户应注意, 在这些情况下的错误处理可能更复杂。 
    
    由于处理延迟操作中的错误与在设置 MAPI\_DEFERRED_ERRORS 标记时处理错误类似, 因此请参阅[延迟 mapi 错误](deferring-mapi-errors.md)以了解详细信息。 
    
- **保留常用属性的缓存**
    
    服务提供程序实现表可通过缓存常用对象属性的副本来减少创建视图所需的时间。 在内存中保存这些属性的副本时, 必须在每次重新生成视图时从对象中检索这些属性。
    
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

