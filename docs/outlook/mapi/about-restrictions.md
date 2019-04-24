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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322118"
---
# <a name="about-restrictions"></a><span data-ttu-id="89a29-103">关于限制</span><span class="sxs-lookup"><span data-stu-id="89a29-103">About Restrictions</span></span>

  
  
<span data-ttu-id="89a29-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="89a29-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="89a29-105">限制是一种将视图中的行数限制为仅包含与特定条件匹配的列的行数的方法。</span><span class="sxs-lookup"><span data-stu-id="89a29-105">A restriction is a way to limit the number of rows in a view to only those rows with values for columns that match specific criteria.</span></span> <span data-ttu-id="89a29-106">对表格使用限制有许多不同的机会。</span><span class="sxs-lookup"><span data-stu-id="89a29-106">There are many different opportunities for using restrictions with tables.</span></span> <span data-ttu-id="89a29-107">例如, 客户端应用程序可以使用限制来筛选由特定人员发送的邮件的内容表, 以搜索不支持属性或已将属性设置为特定值的行, 或查找中的重复收件人消息。</span><span class="sxs-lookup"><span data-stu-id="89a29-107">Client applications can use restrictions, for example, to filter a contents table for messages sent by a particular person, to search for rows that either do not support a property or have set a property to a specific value, or to look for duplicate recipients within a message.</span></span> 
  
<span data-ttu-id="89a29-108">[IMAPITable:: Restrict](imapitable-restrict.md)和[IMAPITable:: FindRow](imapitable-findrow.md)方法用于设置对表的限制。</span><span class="sxs-lookup"><span data-stu-id="89a29-108">The [IMAPITable::Restrict](imapitable-restrict.md) and [IMAPITable::FindRow](imapitable-findrow.md) methods are used to set restrictions on a table.</span></span> <span data-ttu-id="89a29-109">**限制**对表应用限制, 而不检索任何行。</span><span class="sxs-lookup"><span data-stu-id="89a29-109">**Restrict** applies the restriction to the table without retrieving any rows.</span></span> <span data-ttu-id="89a29-110">若要仅检索那些符合限制的行, 则需要对[IMAPITable:: QueryRows](imapitable-queryrows.md)或类似的方法进行后续调用。</span><span class="sxs-lookup"><span data-stu-id="89a29-110">To retrieve only those rows that meet the restriction, a subsequent call to [IMAPITable::QueryRows](imapitable-queryrows.md) or a similar method is required.</span></span> <span data-ttu-id="89a29-111">**FindRow**应用限制, 并检索表中与条件匹配的第一行。</span><span class="sxs-lookup"><span data-stu-id="89a29-111">**FindRow** applies the restriction and retrieves the first row in the table that matches the criteria.</span></span> <span data-ttu-id="89a29-112">**FindRow**应用临时限制, 这仅在呼叫期间存在, 而**限制**应用更永久的限制。</span><span class="sxs-lookup"><span data-stu-id="89a29-112">**FindRow** applies a temporary restriction, which is in existence only for the duration of the call, whereas **Restrict** applies a more permanent restriction.</span></span> 
  
<span data-ttu-id="89a29-113">某些客户端可以使用不在当前列集中的列生成限制。</span><span class="sxs-lookup"><span data-stu-id="89a29-113">Some clients can build a restriction using columns that are not in the current column set.</span></span> <span data-ttu-id="89a29-114">支持这种限制是可选的, 并且支持它的表实施者添加值, 尤其是对于内容表。</span><span class="sxs-lookup"><span data-stu-id="89a29-114">Supporting such a restriction is optional and table implementers that do support it add value, particularly for contents tables.</span></span> <span data-ttu-id="89a29-115">不支持它的表实施者可以从**FindRow**调用中返回**限制**调用或 MAPI_E_NOT_FOUND 值中的 MAPI_E_TOO_COMPLEX 值。</span><span class="sxs-lookup"><span data-stu-id="89a29-115">Table implementers that do not support it can return the MAPI_E_TOO_COMPLEX value from a **Restrict** call or the MAPI_E_NOT_FOUND value from a **FindRow** call.</span></span> 
  
<span data-ttu-id="89a29-116">客户端应注意, 即使提供程序对不在当前列集中的列支持限制, 它们也会获得更好的性能, 具体方法是通过在其对[IMAPITable:: SetColumns](imapitable-setcolumns.md)的限制中指定要使用的列来获得更好的性能。.</span><span class="sxs-lookup"><span data-stu-id="89a29-116">Clients should be aware that, even if the provider does support restrictions on columns not in the current column set, they will get better performance overall by specifying the columns they intend to use in their restrictions with [IMAPITable::SetColumns](imapitable-setcolumns.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="89a29-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89a29-117">See also</span></span>



[<span data-ttu-id="89a29-118">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="89a29-118">MAPI Tables</span></span>](mapi-tables.md)

