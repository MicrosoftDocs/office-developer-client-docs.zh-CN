---
title: 使用技巧表的索引
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
# <a name="tips-for-working-with-tables"></a><span data-ttu-id="96842-103">使用技巧表的索引</span><span class="sxs-lookup"><span data-stu-id="96842-103">Tips for Working with Tables</span></span>

  
  
<span data-ttu-id="96842-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="96842-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="96842-105">使用 MAPI 表与使用 MAPI 表关系数据库类似。</span><span class="sxs-lookup"><span data-stu-id="96842-105">Working with a MAPI table is a little like working with a relational database table.</span></span> <span data-ttu-id="96842-106">用户可以限制视图中的行数和列数并指定其顺序。</span><span class="sxs-lookup"><span data-stu-id="96842-106">A user can limit the number of rows and columns in the view and specify their order.</span></span> <span data-ttu-id="96842-107">可以一次检索一行，也可以成组检索行。</span><span class="sxs-lookup"><span data-stu-id="96842-107">Rows can be retrieved one at a time or in groups.</span></span> <span data-ttu-id="96842-108">跟踪当前位置的游标可以移动到表中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="96842-108">A cursor that keeps track of the current position can be moved to a specific place in the table.</span></span> 
  
<span data-ttu-id="96842-109">为了使用表，客户端使用只读接口 [IMAPITable ： IUnknown](imapitableiunknown.md)，而服务提供商可以使用 **IMAPITable** 或 [ITableData ：IUnknown，](itabledataiunknown.md)具体取决于它们是否拥有该表所基于的数据。</span><span class="sxs-lookup"><span data-stu-id="96842-109">To work with tables, clients use the read-only interface, [IMAPITable : IUnknown](imapitableiunknown.md), whereas service providers, depending on whether they own the data that the table is based on, can use either **IMAPITable** or [ITableData : IUnknown](itabledataiunknown.md).</span></span> <span data-ttu-id="96842-110">这些接口中定义的操作可以归类为表的所有用户都执行的操作，也可以调用和由于更高级而未广泛使用的操作。</span><span class="sxs-lookup"><span data-stu-id="96842-110">The operations defined in these interfaces can be categorized as operations that all users of tables either do or can invoke and operations that are not as widely used because they are more advanced.</span></span> <span data-ttu-id="96842-111">某些高级操作要实施得更复杂;其他不复杂，但对少数 MAPI 组件感兴趣。</span><span class="sxs-lookup"><span data-stu-id="96842-111">Some of the advanced operations are more complex to implement; others are no more complex, but are of interest to a small minority of MAPI components.</span></span> 
  
<span data-ttu-id="96842-112">更常见的操作包括：</span><span class="sxs-lookup"><span data-stu-id="96842-112">The more common operations are:</span></span>
  
- <span data-ttu-id="96842-113">列操作，影响单个列。</span><span class="sxs-lookup"><span data-stu-id="96842-113">Column operations, which affect single columns.</span></span> <span data-ttu-id="96842-114">这些属性包括指定列集中包含的属性以及这些属性的包含顺序。</span><span class="sxs-lookup"><span data-stu-id="96842-114">These include specifying the properties to be included in the column set and the order in which they should be included.</span></span>
    
- <span data-ttu-id="96842-115">行操作，影响单行。</span><span class="sxs-lookup"><span data-stu-id="96842-115">Row operations, which affect single rows.</span></span> <span data-ttu-id="96842-116">其中包括数据检索和维护操作：添加、删除和修改一行或多行。</span><span class="sxs-lookup"><span data-stu-id="96842-116">These include data retrieval and the maintenance operations: adding, deleting, and modifying a single row or rows.</span></span>
    
- <span data-ttu-id="96842-117">影响整个表的全局操作。</span><span class="sxs-lookup"><span data-stu-id="96842-117">Global operations, which affect the entire table.</span></span> <span data-ttu-id="96842-118">其中包括事件通知、搜索和排序。</span><span class="sxs-lookup"><span data-stu-id="96842-118">These include event notification, searching and sorting.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="96842-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96842-119">See also</span></span>



[<span data-ttu-id="96842-120">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="96842-120">MAPI Tables</span></span>](mapi-tables.md)

