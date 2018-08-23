---
title: 为小型表调用 QueryRows
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8c38bb0f-de0b-4d70-9f6d-db652445e137
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 34975677bedccf3f9111985d371e21d482b45584
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589334"
---
# <a name="calling-queryrows-for-small-tables"></a>为小型表调用 QueryRows

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
当检索行时小表，而不是第一个构建限制调用[IMAPITable::QueryRows](imapitable-queryrows.md) 。 由于提供程序必须首先创建一个表，在原始的表中，查找匹配的行，然后将行复制到新表创建限制对性能的影响。 如果表中的行的总数少于 100，则可能要读取的所有行，然后调用[IMAPITable::FindRow](imapitable-findrow.md)查找相应行更有效。 如果仅偶尔需要此信息，这是一个特别是好的策略。 
  
将频繁使用或更长时间的一段时间使用受限或已筛选信息时用于限制的适当时间。 例如，如果您始终需要具有未读邮件的视图，然后限制是正确呼叫使用。
  

