---
title: 为小型表调用 QueryRows
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8c38bb0f-de0b-4d70-9f6d-db652445e137
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8b38dcc485e75f94ccf4f4c3c8c9a57d314465a6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404174"
---
# <a name="calling-queryrows-for-small-tables"></a>为小型表调用 QueryRows

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索小表中的行时, 调用[IMAPITable:: QueryRows](imapitable-queryrows.md) , 而不是首先生成限制。 由于提供程序必须首先创建一个表, 找到原始表中的匹配行, 然后将行复制到新表中, 因此创建限制会影响性能。 如果表中的总行数小于 100, 则读取所有行并调用[IMAPITable:: FindRow](imapitable-findrow.md)以查找适当的行可能会更有效。 如果仅偶尔需要此信息, 则这是一个特别有用的策略。 
  
使用限制的正确时间是在较长的一段时间内使用受限制或筛选的信息, 或者频繁使用这些信息。 例如, 如果始终需要具有未读邮件的视图, 则限制是要使用的正确调用。
  

