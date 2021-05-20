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
  
**IMAPITable** 接口包括三种异步操作方法和三种用于控制异步操作的方法。 下表列出了这些方法： 
  
|**异步操作**|**异步控件方法**|
|:-----|:-----|
|[IMAPITable::SetColumns](imapitable-setcolumns.md) <br/> |[IMAPITable::GetStatus](imapitable-getstatus.md) <br/> |
|[IMAPITable::Restrict](imapitable-restrict.md) <br/> |[IMAPITable::Abort](imapitable-abort.md) <br/> |
|[IMAPITable::SortTable](imapitable-sorttable.md) <br/> |[IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md) <br/> |
   
**检索有关表的类型和当前操作的状态信息**
  
- 调用 [IMAPITable：：GetStatus](imapitable-getstatus.md)。 使用 **GetStatus，** 表用户可以确定表是静态表还是动态表、操作正在进行还是已完成，以及已完成操作是否发生了错误。 例如，如果客户端因时间过长而需要取消排序操作，则客户端可以首先调用 **GetStatus** 来确定排序操作实际上是否正在处理。 然后，客户端可以调用 [IMAPITable：：Abort](imapitable-abort.md) 以停止它。 
    
**在异步任务完成之前暂停活动**
  
- 调用 [IMAPITable：：WaitForCompletion](imapitable-waitforcompletion.md)。 通过 **调用 WaitForCompletion，** 任务可以不间断地完成。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

