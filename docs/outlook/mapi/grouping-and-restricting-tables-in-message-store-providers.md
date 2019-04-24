---
title: 对邮件存储提供程序中的表进行分组和限制
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01df4be4-98a1-4159-a06d-9ccf4337198f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8a45a9fd0d40c16d110fd52be1ac1117e1dd4d04
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299410"
---
# <a name="grouping-and-restricting-tables-in-message-store-providers"></a><span data-ttu-id="602d9-103">对邮件存储提供程序中的表进行分组和限制</span><span class="sxs-lookup"><span data-stu-id="602d9-103">Grouping and Restricting Tables in Message Store Providers</span></span>

  
  
<span data-ttu-id="602d9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="602d9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="602d9-105">客户端应用程序经常允许用户控制文件夹内容的显示方式。</span><span class="sxs-lookup"><span data-stu-id="602d9-105">Client applications frequently allow users some control over how the contents of a folder are displayed.</span></span> <span data-ttu-id="602d9-106">通常情况下, 用户可以选择根据一个或多个邮件属性的值对邮件进行分组, 也可以选择排除符合特定条件的邮件。</span><span class="sxs-lookup"><span data-stu-id="602d9-106">Typically, a user can choose to have messages grouped according to the value of one or more message properties, or can choose to exclude messages that match certain criteria.</span></span> <span data-ttu-id="602d9-107">这是通过使用[IMAPITable: IUnknown](imapitableiunknown.md)接口来完成的。</span><span class="sxs-lookup"><span data-stu-id="602d9-107">This is done by using the [IMAPITable : IUnknown](imapitableiunknown.md) interface.</span></span> <span data-ttu-id="602d9-108">客户端应用程序可以将从表返回的行限制为用户指定的任何条件。</span><span class="sxs-lookup"><span data-stu-id="602d9-108">Client applications can restrict the rows returned from the table to whatever criteria the user specifies.</span></span> <span data-ttu-id="602d9-109">因此, 邮件存储提供程序需要实现以下**IMAPITable**方法。</span><span class="sxs-lookup"><span data-stu-id="602d9-109">Therefore, a message store provider needs to implement the following **IMAPITable** methods.</span></span> 
  
|<span data-ttu-id="602d9-110">IMAPITable \* \* 方法 \* \*</span><span class="sxs-lookup"><span data-stu-id="602d9-110">\*\*\*\*IMAPITable\*\* method\*\*</span></span>|<span data-ttu-id="602d9-111">**Description**</span><span class="sxs-lookup"><span data-stu-id="602d9-111">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="602d9-112">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="602d9-112">IMAPITable::FindRow</span></span>](imapitable-findrow.md) <br/> |<span data-ttu-id="602d9-113">返回与指定条件匹配的表格行。</span><span class="sxs-lookup"><span data-stu-id="602d9-113">Returns table rows that match the specified criteria.</span></span>  <br/> |
|[<span data-ttu-id="602d9-114">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="602d9-114">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md) <br/> |<span data-ttu-id="602d9-115">返回表中的一组列或当前使用的列的集合。</span><span class="sxs-lookup"><span data-stu-id="602d9-115">Returns the set of columns in a table or the set of currently used columns.</span></span>  <br/> |
|[<span data-ttu-id="602d9-116">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="602d9-116">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md) <br/> |<span data-ttu-id="602d9-117">从给定位置开始, 返回表中的一个或多个行。</span><span class="sxs-lookup"><span data-stu-id="602d9-117">Returns one or more rows from a table, starting from a given position.</span></span>  <br/> |
|[<span data-ttu-id="602d9-118">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="602d9-118">IMAPITable::Restrict</span></span>](imapitable-restrict.md) <br/> |<span data-ttu-id="602d9-119">对表应用限制, 以便随后对**FindRow**的调用仅返回与该限制匹配的行。</span><span class="sxs-lookup"><span data-stu-id="602d9-119">Applies a restriction to a table so that subsequent calls to **FindRow** return only rows that match the restriction.</span></span>  <br/> |
|[<span data-ttu-id="602d9-120">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="602d9-120">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md) <br/> |<span data-ttu-id="602d9-121">指定从表中检索行时应返回的列。</span><span class="sxs-lookup"><span data-stu-id="602d9-121">Specifies which columns should be returned when rows are retrieved from the table.</span></span>  <br/> |
   
<span data-ttu-id="602d9-122">实施限制可能非常复杂;有关详细信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="602d9-122">Restrictions can be complex to implement; for more information, see [About Restrictions](about-restrictions.md).</span></span> <span data-ttu-id="602d9-123">有关实现表的详细信息, 请参阅[MAPI 表](mapi-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="602d9-123">For more information about implementing tables, see [MAPI Tables](mapi-tables.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="602d9-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="602d9-124">See also</span></span>



[<span data-ttu-id="602d9-125">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="602d9-125">Message Store Features</span></span>](message-store-features.md)

