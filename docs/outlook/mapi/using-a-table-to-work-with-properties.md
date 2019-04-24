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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329699"
---
# <a name="using-a-table-to-work-with-properties"></a>使用表处理属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
许多属性都可从支持它们的对象和表中的列使用。 只要有可能, 请通过表检索这些属性。
  
调用[IMAPITable:: SetColumns](imapitable-setcolumns.md)以包含客户端所需的所有属性和[IMAPITable:: QueryRows](imapitable-queryrows.md)检索表的所有行。 
  
这两个呼叫通常足以检索足够的信息以向用户显示, 并且经常需要进行任何必要的内部处理, 从而调用**OpenEntry**以打开不必要的对象。 
  
只有两个例外:
  
- 如果该属性超过255个字节。 * * IMAPITable * * 接口可能不会返回整个属性值, 而是将其截断为255字节。 不过, 请考虑这种折衷。 如果要向用户显示此数据, 则255字节可能足以满足文本字段 (如注释) 的需要。 
    
- 如果需要表中单个行的特定属性。 在这种情况下, 不需要创建包含永远不使用的属性的表。 大多数时候, 所有行都需要相同的属性。
    

