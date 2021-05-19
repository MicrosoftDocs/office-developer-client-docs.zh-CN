---
title: 设置列和限制后对表进行排序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57db0314-1df0-4fd2-b443-223b0512f1ad
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 62220794f325165e67db5397da2795d49959ef60
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409879"
---
# <a name="sorting-tables-after-setting-columns-and-restrictions"></a>设置列和限制后对表进行排序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当需要限制已排序表的视图时，请始终按以下顺序进行 **以下 IMAPITable** 调用： 
  
1. [用于定义列集的 IMAPITable：：SetColumns。](imapitable-setcolumns.md) 
    
2. [IMAPITable：：Restrict](imapitable-restrict.md) 施加限制。 
    
3. [IMAPITable：：SortTable](imapitable-sorttable.md) 以执行排序。 
    
如果已排序表已分类，则在必要时在 **SortTable** 调用后调用 [IMAPITable：：SetCollapseState。](imapitable-setcollapsestate.md) 这种调用顺序非常重要，因为大多数服务提供商将表排序为实现最佳性能的最后一项任务。 例如，如果邮件存储提供程序必须对文件夹内容表进行分类，然后才能施加限制，则在处理限制期间将移除此分类。 需要第二个分类。 
  

