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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412511"
---
# <a name="tips-for-better-table-performance"></a>表性能提升提示
  
**适用于**：Outlook 2013 | Outlook 2016 
  
由于许多表操作可能非常耗时且无法指示进度，因此使用以下技术提高性能会很有帮助：
  
- **按 [正确顺序进行 IMAPITable ： IUnknown](imapitableiunknown.md) 调用**
    
   客户端和服务提供商可以通过多种方式使用表。 他们可以使用默认列集和排序顺序打开表并检索所有行的数据。 或者，他们可以通过更改列集、更改排序顺序或建立限制来缩小表的范围来修改表的此默认视图。 在检索任何数据之前打算执行一个或多个这些操作的用户应按以下顺序执行这些操作：
    
    1. 使用 [IMAPITable：：SetColumns 定义列集](imapitable-setcolumns.md)。
        
    2. 与 [IMAPITable：：Restrict 建立限制](imapitable-restrict.md)。
        
    3. 使用 [IMAPITable：：SortTable 定义排序顺序](imapitable-sorttable.md)。
    
    按此顺序执行这些任务将限制排序的行数和列数，从而提高性能。
    
- **如果可能，使用 TBL_BATCH 标志延迟操作**
    
    通过设置方法上的 TBL BATCH 标志，表实施者可以在处理其中任何一个调用之前 \_ 收集多个调用。 不要对远程服务器进行潜在的多次调用;表实施者可以创建一个表，一次执行所有操作。 在需要操作结果之前，不会评估它们。 
    
    例如，当客户端调用 [IMAPITable：：Restrict](imapitable-restrict.md) 以指定设置了 TBL 批处理标志的限制时，在客户端调用 \_ [IMAPITable：：QueryRows](imapitable-queryrows.md) 检索数据之前，该限制不一定生效。 这允许表实施者将两个调用的工作合并为一个。 利用 TBL 批处理标志的表用户应注意，在这些条件下的错误处理 \_ 可能更加复杂。 
    
    由于处理延迟操作中的错误与设置 MAPI DEFERRED_ERRORS 标志时处理错误类似，有关详细信息，请参阅 \_ [Deferring MAPI Errors。](deferring-mapi-errors.md) 
    
- **保留常用属性的缓存**
    
    通过缓存常用对象属性的副本，实现表的服务提供商可以减少创建视图所花的时间。 将这些属性的副本保存在内存中可节省每次必须重新生成视图时从对象中检索这些属性。
    
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

