---
title: 关于异步表操作
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57219d96-bd9e-4e9a-b34a-dd3aad97bfd9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eebc04e2263b4a2037e167bd464a31d298b84664
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439567"
---
# <a name="about-asynchronous-table-operations"></a>关于异步表操作
 
**适用于**：Outlook 2013 | Outlook 2016 
  
**IMAPITable**接口包括三种异步操作方法, 以及用于控制异步操作的三种方法。 下表列出了这些方法: 
  
|**异步操作**|**异步控制方法**|
|:-----|:-----|
|[IMAPITable::SetColumns](imapitable-setcolumns.md) <br/> |[IMAPITable::GetStatus](imapitable-getstatus.md) <br/> |
|[IMAPITable::Restrict](imapitable-restrict.md) <br/> |[IMAPITable::Abort](imapitable-abort.md) <br/> |
|[IMAPITable::SortTable](imapitable-sorttable.md) <br/> |[IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md) <br/> |
   
**检索有关表的类型和当前操作的状态信息**
  
- 调用[IMAPITable:: GetStatus](imapitable-getstatus.md)。 通过**GetStatus**, 表用户可以确定表是静态的还是动态的, 如果某个操作正在进行中或已完成, 以及在已完成的操作中是否发生了错误。 例如, 如果客户端需要取消某个排序操作, 因为它花费的时间太长, 则客户端可以先调用**GetStatus** , 以确定当前是否正在处理排序操作。 然后, 客户端可以调用[IMAPITable:: Abort](imapitable-abort.md)停止它。 
    
**挂起活动直到异步任务完成**
  
- 调用[IMAPITable:: WaitForCompletion](imapitable-waitforcompletion.md)。 通过调用**WaitForCompletion** , 可以在不中断的情况下完成任务。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

