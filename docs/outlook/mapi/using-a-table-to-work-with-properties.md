---
title: 使用表处理属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c18ed9f7-c053-4453-b0b1-06234cdfb025
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 59196f136c422be912ac2460cbbd25d8bc2e3330
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439910"
---
# <a name="using-a-table-to-work-with-properties"></a>使用表处理属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
许多属性都从支持这些属性的对象和表上的列提供。 如果可能，请通过表检索这些属性。
  
调用 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 以包含客户端需要的所有属性，并调用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 检索表的所有行。 
  
这两个调用通常足以检索向用户显示的足够信息，并且通常足以用于任何必要的内部处理，因此调用 **OpenEntry** 以打开对象是不必要的。 
  
只有两个例外：
  
- 如果属性超过 255 字节。 ** IMAPITable ** 接口可能不会返回整个属性值，而是以 255 字节为单位截断它。 但是，考虑此权衡。 如果要向用户显示此数据，则对于文本字段（如注释）来说，255 个字节可能就足够了。 
    
- 如果需要表中的单个行中的特定属性。 在这种情况下，不必创建具有永远不会使用的属性的表。 大多数情况下，需要所有行的相同属性。
    

