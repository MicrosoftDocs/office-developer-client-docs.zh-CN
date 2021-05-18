---
title: 调用小型表的 QueryRows
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
# <a name="calling-queryrows-for-small-tables"></a>调用小型表的 QueryRows

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从小表中检索行时，请调用 [IMAPITable：：QueryRows，](imapitable-queryrows.md) 而不是首先构建限制。 创建限制会影响性能，因为提供程序必须先创建一个表，在原始表中查找匹配的行，然后将这些行复制到新表中。 如果表中的总行数小于 100，则读取所有行，然后调用 [IMAPITable：：FindRow](imapitable-findrow.md) 查找相应行可能更有效。 如果仅偶尔需要此信息，则这是一项特别不错的策略。 
  
使用限制的正确时间是在受限或经过筛选的信息将在较长时间内使用或频繁使用时。 例如，如果始终需要包含未读邮件的视图，则限制是使用的正确调用。
  

