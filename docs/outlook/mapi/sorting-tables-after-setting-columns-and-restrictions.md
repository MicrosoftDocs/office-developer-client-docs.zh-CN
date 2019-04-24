---
title: 设置列和限制后对表排序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57db0314-1df0-4fd2-b443-223b0512f1ad
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 62220794f325165e67db5397da2795d49959ef60
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344483"
---
# <a name="sorting-tables-after-setting-columns-and-restrictions"></a>设置列和限制后对表排序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果需要限制已排序的表的视图, 请始终按以下顺序发出以下**IMAPITable**调用: 
  
1. [IMAPITable:: SetColumns](imapitable-setcolumns.md)定义列集。 
    
2. [IMAPITable:: Restrict](imapitable-restrict.md)以施加限制。 
    
3. [IMAPITable:: SortTable](imapitable-sorttable.md)执行排序。 
    
如果对已排序的表进行了分类, 请在**SortTable**调用后调用[IMAPITable:: SetCollapseState](imapitable-setcollapsestate.md)(如有必要)。 这种呼叫顺序非常重要, 因为大多数服务提供程序都会将表作为最后一个任务进行排序以实现最佳性能。 例如, 如果在可以强制实施限制之前, 邮件存储提供程序必须对文件夹内容表进行分类, 则在处理此限制的过程中将删除此分类。 第二个分类是必需的。 
  

