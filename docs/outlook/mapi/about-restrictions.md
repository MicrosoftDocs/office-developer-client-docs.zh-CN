---
title: 关于限制
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e119fa20-08b8-4c8d-93fc-56037220890d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 139526937380273703a96f91f2bae02a79debc76
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433106"
---
# <a name="about-restrictions"></a><span data-ttu-id="c6895-103">关于限制</span><span class="sxs-lookup"><span data-stu-id="c6895-103">About Restrictions</span></span>

  
  
<span data-ttu-id="c6895-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c6895-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c6895-105">限制是一种将视图中的行数限制为仅具有与特定条件匹配的列值的行的方法。</span><span class="sxs-lookup"><span data-stu-id="c6895-105">A restriction is a way to limit the number of rows in a view to only those rows with values for columns that match specific criteria.</span></span> <span data-ttu-id="c6895-106">对表使用限制有许多不同的机会。</span><span class="sxs-lookup"><span data-stu-id="c6895-106">There are many different opportunities for using restrictions with tables.</span></span> <span data-ttu-id="c6895-107">例如，客户端应用程序可以使用限制来筛选特定人员发送的邮件的内容表，搜索不支持属性或将属性设置为特定值的行，或在邮件中查找重复的收件人。</span><span class="sxs-lookup"><span data-stu-id="c6895-107">Client applications can use restrictions, for example, to filter a contents table for messages sent by a particular person, to search for rows that either do not support a property or have set a property to a specific value, or to look for duplicate recipients within a message.</span></span> 
  
<span data-ttu-id="c6895-108">[IMAPITable：：Restrict](imapitable-restrict.md)和[IMAPITable：：FindRow](imapitable-findrow.md)方法用于对表设置限制。</span><span class="sxs-lookup"><span data-stu-id="c6895-108">The [IMAPITable::Restrict](imapitable-restrict.md) and [IMAPITable::FindRow](imapitable-findrow.md) methods are used to set restrictions on a table.</span></span> <span data-ttu-id="c6895-109">**Restrict** 将限制应用于表，而不检索任何行。</span><span class="sxs-lookup"><span data-stu-id="c6895-109">**Restrict** applies the restriction to the table without retrieving any rows.</span></span> <span data-ttu-id="c6895-110">若要仅检索满足限制的行，需要后续调用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 或类似方法。</span><span class="sxs-lookup"><span data-stu-id="c6895-110">To retrieve only those rows that meet the restriction, a subsequent call to [IMAPITable::QueryRows](imapitable-queryrows.md) or a similar method is required.</span></span> <span data-ttu-id="c6895-111">**FindRow** 应用限制并检索表中匹配条件的第一行。</span><span class="sxs-lookup"><span data-stu-id="c6895-111">**FindRow** applies the restriction and retrieves the first row in the table that matches the criteria.</span></span> <span data-ttu-id="c6895-112">**FindRow** 应用临时限制，此限制仅在调用期间存在， **而 Restrict** 应用更永久的限制。</span><span class="sxs-lookup"><span data-stu-id="c6895-112">**FindRow** applies a temporary restriction, which is in existence only for the duration of the call, whereas **Restrict** applies a more permanent restriction.</span></span> 
  
<span data-ttu-id="c6895-113">某些客户端可以使用当前列集外列构建限制。</span><span class="sxs-lookup"><span data-stu-id="c6895-113">Some clients can build a restriction using columns that are not in the current column set.</span></span> <span data-ttu-id="c6895-114">支持此类限制是可选的，并且支持此限制的表实施者会增加值，特别是对于内容表。</span><span class="sxs-lookup"><span data-stu-id="c6895-114">Supporting such a restriction is optional and table implementers that do support it add value, particularly for contents tables.</span></span> <span data-ttu-id="c6895-115">不支持它的表实现程序可以从 Restrict MAPI_E_TOO_COMPLEX **返回** 值，也可以从 **FindRow** MAPI_E_NOT_FOUND返回值。</span><span class="sxs-lookup"><span data-stu-id="c6895-115">Table implementers that do not support it can return the MAPI_E_TOO_COMPLEX value from a **Restrict** call or the MAPI_E_NOT_FOUND value from a **FindRow** call.</span></span> 
  
<span data-ttu-id="c6895-116">客户端应注意，即使提供程序支持对不在当前列集的列的限制，它们也会通过指定他们在 [与 IMAPITable：：SetColumns](imapitable-setcolumns.md)的限制中打算使用的列，获得更好的整体性能。</span><span class="sxs-lookup"><span data-stu-id="c6895-116">Clients should be aware that, even if the provider does support restrictions on columns not in the current column set, they will get better performance overall by specifying the columns they intend to use in their restrictions with [IMAPITable::SetColumns](imapitable-setcolumns.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c6895-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6895-117">See also</span></span>



[<span data-ttu-id="c6895-118">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="c6895-118">MAPI Tables</span></span>](mapi-tables.md)

