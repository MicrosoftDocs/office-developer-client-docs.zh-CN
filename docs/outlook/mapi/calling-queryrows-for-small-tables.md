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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331624"
---
# <a name="calling-queryrows-for-small-tables"></a><span data-ttu-id="13cff-103">为小型表调用 QueryRows</span><span class="sxs-lookup"><span data-stu-id="13cff-103">Calling QueryRows for Small Tables</span></span>

  
  
<span data-ttu-id="13cff-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="13cff-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="13cff-105">检索小表中的行时, 调用[IMAPITable:: QueryRows](imapitable-queryrows.md) , 而不是首先生成限制。</span><span class="sxs-lookup"><span data-stu-id="13cff-105">When retrieving rows from a small table, call [IMAPITable::QueryRows](imapitable-queryrows.md) instead of first building a restriction.</span></span> <span data-ttu-id="13cff-106">由于提供程序必须首先创建一个表, 找到原始表中的匹配行, 然后将行复制到新表中, 因此创建限制会影响性能。</span><span class="sxs-lookup"><span data-stu-id="13cff-106">Creating a restriction impacts performance because the provider must first create a table, find the matching rows in the original table, and then copy the rows to the new table.</span></span> <span data-ttu-id="13cff-107">如果表中的总行数小于 100, 则读取所有行并调用[IMAPITable:: FindRow](imapitable-findrow.md)以查找适当的行可能会更有效。</span><span class="sxs-lookup"><span data-stu-id="13cff-107">If the total number of rows in the table is less than 100, it is probably more effective to read all of the rows and then call [IMAPITable::FindRow](imapitable-findrow.md) to find the appropriate row.</span></span> <span data-ttu-id="13cff-108">如果仅偶尔需要此信息, 则这是一个特别有用的策略。</span><span class="sxs-lookup"><span data-stu-id="13cff-108">This is a particularly good strategy if this information is needed only occasionally.</span></span> 
  
<span data-ttu-id="13cff-109">使用限制的正确时间是在较长的一段时间内使用受限制或筛选的信息, 或者频繁使用这些信息。</span><span class="sxs-lookup"><span data-stu-id="13cff-109">The proper time to use a restriction is when the restricted or filtered information will be used over a longer period of time or used frequently.</span></span> <span data-ttu-id="13cff-110">例如, 如果始终需要具有未读邮件的视图, 则限制是要使用的正确调用。</span><span class="sxs-lookup"><span data-stu-id="13cff-110">For instance, if you always need a view with unread messages, then a restriction is the proper call to use.</span></span>
  

