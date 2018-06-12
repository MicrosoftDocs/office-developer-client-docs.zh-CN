---
title: 有关限制
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e119fa20-08b8-4c8d-93fc-56037220890d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d7294527fcd557ae2d4824b9a3215ff464f62c2a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774476"
---
# <a name="about-restrictions"></a><span data-ttu-id="6d9dd-103">有关限制</span><span class="sxs-lookup"><span data-stu-id="6d9dd-103">About Restrictions</span></span>

  
  
<span data-ttu-id="6d9dd-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6d9dd-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6d9dd-105">限制是一种方法来限制为仅与特定条件匹配的列的值这些行视图中的行数。</span><span class="sxs-lookup"><span data-stu-id="6d9dd-105">A restriction is a way to limit the number of rows in a view to only those rows with values for columns that match specific criteria.</span></span> <span data-ttu-id="6d9dd-106">有许多不同的机会，使用的表的限制。</span><span class="sxs-lookup"><span data-stu-id="6d9dd-106">There are many different opportunities for using restrictions with tables.</span></span> <span data-ttu-id="6d9dd-107">客户端应用程序可用于限制，例如，筛选搜索行的不支持属性，或具有属性设置为特定值，或查找内的重复收件人由特定人员，发送的邮件内容表消息。</span><span class="sxs-lookup"><span data-stu-id="6d9dd-107">Client applications can use restrictions, for example, to filter a contents table for messages sent by a particular person, to search for rows that either do not support a property or have set a property to a specific value, or to look for duplicate recipients within a message.</span></span> 
  
<span data-ttu-id="6d9dd-108">[IMAPITable::Restrict](imapitable-restrict.md)和[IMAPITable::FindRow](imapitable-findrow.md)方法用于设置对表格的限制。</span><span class="sxs-lookup"><span data-stu-id="6d9dd-108">The [IMAPITable::Restrict](imapitable-restrict.md) and [IMAPITable::FindRow](imapitable-findrow.md) methods are used to set restrictions on a table.</span></span> <span data-ttu-id="6d9dd-109">**限制**对表格中应用此限制，而不检索任何行。</span><span class="sxs-lookup"><span data-stu-id="6d9dd-109">**Restrict** applies the restriction to the table without retrieving any rows.</span></span> <span data-ttu-id="6d9dd-110">若要检索满足限制的行，则需要后续调用[IMAPITable::QueryRows](imapitable-queryrows.md)或类似的方法。</span><span class="sxs-lookup"><span data-stu-id="6d9dd-110">To retrieve only those rows that meet the restriction, a subsequent call to [IMAPITable::QueryRows](imapitable-queryrows.md) or a similar method is required.</span></span> <span data-ttu-id="6d9dd-111">**FindRow**应用此限制，并检索与条件匹配的表中的第一行。</span><span class="sxs-lookup"><span data-stu-id="6d9dd-111">**FindRow** applies the restriction and retrieves the first row in the table that matches the criteria.</span></span> <span data-ttu-id="6d9dd-112">**FindRow**应用临时限制，这是中存在仅用于呼叫的持续时间，而**Restrict**应用更永久限制。</span><span class="sxs-lookup"><span data-stu-id="6d9dd-112">**FindRow** applies a temporary restriction, which is in existence only for the duration of the call, whereas **Restrict** applies a more permanent restriction.</span></span> 
  
<span data-ttu-id="6d9dd-113">某些客户端可以构建限制使用当前列中不包含的列。</span><span class="sxs-lookup"><span data-stu-id="6d9dd-113">Some clients can build a restriction using columns that are not in the current column set.</span></span> <span data-ttu-id="6d9dd-114">支持这样的限制是可选的支持它的表实施添加值，特别是对于内容表。</span><span class="sxs-lookup"><span data-stu-id="6d9dd-114">Supporting such a restriction is optional and table implementers that do support it add value, particularly for contents tables.</span></span> <span data-ttu-id="6d9dd-115">不支持的表实施可以从**Restrict**呼叫或从**FindRow**呼叫 MAPI_E_NOT_FOUND 值返回 MAPI_E_TOO_COMPLEX 值。</span><span class="sxs-lookup"><span data-stu-id="6d9dd-115">Table implementers that do not support it can return the MAPI_E_TOO_COMPLEX value from a **Restrict** call or the MAPI_E_NOT_FOUND value from a **FindRow** call.</span></span> 
  
<span data-ttu-id="6d9dd-116">客户端应注意，即使不在当前的列组列上提供程序支持的限制，他们将得到更好的总体性能，通过指定他们想要在其限制与[IMAPITable::SetColumns](imapitable-setcolumns.md)中使用的列.</span><span class="sxs-lookup"><span data-stu-id="6d9dd-116">Clients should be aware that, even if the provider does support restrictions on columns not in the current column set, they will get better performance overall by specifying the columns they intend to use in their restrictions with [IMAPITable::SetColumns](imapitable-setcolumns.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6d9dd-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d9dd-117">See also</span></span>



[<span data-ttu-id="6d9dd-118">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="6d9dd-118">MAPI Tables</span></span>](mapi-tables.md)

