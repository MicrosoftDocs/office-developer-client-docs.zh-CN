---
title: 有关异步表操作
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57219d96-bd9e-4e9a-b34a-dd3aad97bfd9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 99bff153d4ce4bac3f85e0ed0feeaffafa6bf3f6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774464"
---
# <a name="about-asynchronous-table-operations"></a>有关异步表操作
 
**适用于**： Outlook 
  
**IMAPITable**界面包括异步操作的三种方法和用于控制异步操作的三种方法。 下表列出了这些方法： 
  
|**异步操作**|**异步控制方法**|
|:-----|:-----|
|[IMAPITable::SetColumns](imapitable-setcolumns.md) <br/> |[IMAPITable::GetStatus](imapitable-getstatus.md) <br/> |
|[IMAPITable::Restrict](imapitable-restrict.md) <br/> |[IMAPITable::Abort](imapitable-abort.md) <br/> |
|[IMAPITable::SortTable](imapitable-sorttable.md) <br/> |[IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md) <br/> |
   
**若要检索有关表的类型和当前操作的状态信息**
  
- 调用[IMAPITable::GetStatus](imapitable-getstatus.md)。 使用**GetStatus**，表用户可以确定是否表是静态或动态，如果操作正在进行或完成后，而如果出现错误从已完成的操作。 例如，如果客户端需要取消排序操作，因为时间太长时间，客户端可以先调用**GetStatus**以确定是否，实际上，排序操作目前处理。 然后，客户端可以调用[IMAPITable::Abort](imapitable-abort.md)以将其停止。 
    
**挂起活动，直到异步任务已完成**
  
- 调用[IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md)。 调用**WaitForCompletion**允许任务完成不会中断。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

