---
title: 使用表格的提示
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: adb4d589-7e03-4222-8717-898ef397c6b6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8f310c6331df941d3093b276b6dec47f740412e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439735"
---
# <a name="tips-for-working-with-tables"></a><span data-ttu-id="297c8-103">使用表格的提示</span><span class="sxs-lookup"><span data-stu-id="297c8-103">Tips for Working with Tables</span></span>

  
  
<span data-ttu-id="297c8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="297c8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="297c8-105">使用 MAPI 表与处理关系数据库表有点相似。</span><span class="sxs-lookup"><span data-stu-id="297c8-105">Working with a MAPI table is a little like working with a relational database table.</span></span> <span data-ttu-id="297c8-106">用户可以限制视图中的行数和列数, 并指定它们的顺序。</span><span class="sxs-lookup"><span data-stu-id="297c8-106">A user can limit the number of rows and columns in the view and specify their order.</span></span> <span data-ttu-id="297c8-107">可以一次检索一个行, 也可以按组检索行。</span><span class="sxs-lookup"><span data-stu-id="297c8-107">Rows can be retrieved one at a time or in groups.</span></span> <span data-ttu-id="297c8-108">可以将当前位置跟踪的游标移到表中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="297c8-108">A cursor that keeps track of the current position can be moved to a specific place in the table.</span></span> 
  
<span data-ttu-id="297c8-109">若要使用表, 客户端将使用只读接口 ( [imapitable: IUnknown](imapitableiunknown.md), 而服务提供程序), 这取决于其是否拥有表所基于的数据, 可以使用**IMAPITable**或[ITableData: IUnknown](itabledataiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="297c8-109">To work with tables, clients use the read-only interface, [IMAPITable : IUnknown](imapitableiunknown.md), whereas service providers, depending on whether they own the data that the table is based on, can use either **IMAPITable** or [ITableData : IUnknown](itabledataiunknown.md).</span></span> <span data-ttu-id="297c8-110">可以将这些接口中定义的操作作为所有表的用户执行或可以调用的操作和由于更高级而不会被广泛使用的操作进行分类的操作。</span><span class="sxs-lookup"><span data-stu-id="297c8-110">The operations defined in these interfaces can be categorized as operations that all users of tables either do or can invoke and operations that are not as widely used because they are more advanced.</span></span> <span data-ttu-id="297c8-111">某些高级操作更复杂, 可以实现;有些不复杂, 但对少数 MAPI 组件很有意义。</span><span class="sxs-lookup"><span data-stu-id="297c8-111">Some of the advanced operations are more complex to implement; others are no more complex, but are of interest to a small minority of MAPI components.</span></span> 
  
<span data-ttu-id="297c8-112">更常见的操作是:</span><span class="sxs-lookup"><span data-stu-id="297c8-112">The more common operations are:</span></span>
  
- <span data-ttu-id="297c8-113">影响单个列的列操作。</span><span class="sxs-lookup"><span data-stu-id="297c8-113">Column operations, which affect single columns.</span></span> <span data-ttu-id="297c8-114">这些属性包括指定要包含在列集中的属性以及应包含的属性顺序。</span><span class="sxs-lookup"><span data-stu-id="297c8-114">These include specifying the properties to be included in the column set and the order in which they should be included.</span></span>
    
- <span data-ttu-id="297c8-115">行操作, 它会影响单个行。</span><span class="sxs-lookup"><span data-stu-id="297c8-115">Row operations, which affect single rows.</span></span> <span data-ttu-id="297c8-116">其中包括数据检索和维护操作: 添加、删除和修改单个行或行。</span><span class="sxs-lookup"><span data-stu-id="297c8-116">These include data retrieval and the maintenance operations: adding, deleting, and modifying a single row or rows.</span></span>
    
- <span data-ttu-id="297c8-117">全局操作, 这将影响整个表。</span><span class="sxs-lookup"><span data-stu-id="297c8-117">Global operations, which affect the entire table.</span></span> <span data-ttu-id="297c8-118">其中包括事件通知、搜索和排序。</span><span class="sxs-lookup"><span data-stu-id="297c8-118">These include event notification, searching and sorting.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="297c8-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="297c8-119">See also</span></span>



[<span data-ttu-id="297c8-120">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="297c8-120">MAPI Tables</span></span>](mapi-tables.md)

