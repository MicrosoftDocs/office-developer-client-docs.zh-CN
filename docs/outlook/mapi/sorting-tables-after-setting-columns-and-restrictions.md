---
title: 设置列和限制后对表排序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57db0314-1df0-4fd2-b443-223b0512f1ad
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9f975ed1b9036bce5ed225b2a9020262260f4f57
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572142"
---
# <a name="sorting-tables-after-setting-columns-and-restrictions"></a>设置列和限制后对表排序

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
当您需要限制排序的表的视图时，请始终按以下顺序进行以下**IMAPITable**呼叫： 
  
1. [IMAPITable::SetColumns](imapitable-setcolumns.md)定义列设置。 
    
2. [IMAPITable::Restrict](imapitable-restrict.md)施加限制。 
    
3. [IMAPITable::SortTable](imapitable-sorttable.md)执行排序。 
    
如果归类排序的表，向发起呼叫[IMAPITable::SetCollapseState](imapitable-setcollapsestate.md)，如有必要之后**SortTable**呼叫。 此呼叫的顺序很重要，因为大多数服务提供商表格进行排序作为最后一项任务以实现最佳性能。 如果，例如，消息存储提供程序必须分类文件夹内容表之前可以施加限制，将该限制的处理过程中删除此分类。 第二个分类是必需的。 
  

