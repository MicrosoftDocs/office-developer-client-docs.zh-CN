---
title: 使用表格的提示
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: adb4d589-7e03-4222-8717-898ef397c6b6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 451bab57d4e2e8669a25d119f9ce28a8f78e628f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778968"
---
# <a name="tips-for-working-with-tables"></a><span data-ttu-id="2c09e-103">使用表格的提示</span><span class="sxs-lookup"><span data-stu-id="2c09e-103">Tips for Working with Tables</span></span>

  
  
<span data-ttu-id="2c09e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2c09e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2c09e-105">使用 MAPI 表是一个小喜欢使用关系数据库表。</span><span class="sxs-lookup"><span data-stu-id="2c09e-105">Working with a MAPI table is a little like working with a relational database table.</span></span> <span data-ttu-id="2c09e-106">用户可以限制的行和视图中的列数，并指定它们的顺序。</span><span class="sxs-lookup"><span data-stu-id="2c09e-106">A user can limit the number of rows and columns in the view and specify their order.</span></span> <span data-ttu-id="2c09e-107">行可以检索到的一个一次或组中。</span><span class="sxs-lookup"><span data-stu-id="2c09e-107">Rows can be retrieved one at a time or in groups.</span></span> <span data-ttu-id="2c09e-108">可以将跟踪的当前位置光标移动到表中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="2c09e-108">A cursor that keeps track of the current position can be moved to a specific place in the table.</span></span> 
  
<span data-ttu-id="2c09e-109">若要使用表，客户端使用的只读接口， [IMAPITable: IUnknown](imapitableiunknown.md)，而服务提供商，具体取决于他们所拥有的数据的表基于是否可以使用任一**IMAPITable**或[ITableData: IUnknown](itabledataiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="2c09e-109">To work with tables, clients use the read-only interface, [IMAPITable : IUnknown](imapitableiunknown.md), whereas service providers, depending on whether they own the data that the table is based on, can use either **IMAPITable** or [ITableData : IUnknown](itabledataiunknown.md).</span></span> <span data-ttu-id="2c09e-110">在这些接口定义的操作可分类为操作的表的所有用户执行操作或可以调用和尚未为广泛使用因为它们更高级的操作。</span><span class="sxs-lookup"><span data-stu-id="2c09e-110">The operations defined in these interfaces can be categorized as operations that all users of tables either do or can invoke and operations that are not as widely used because they are more advanced.</span></span> <span data-ttu-id="2c09e-111">某些高级操作是实现; 起来较复杂其他人不更复杂，但对少数人的 MAPI 组件感兴趣。</span><span class="sxs-lookup"><span data-stu-id="2c09e-111">Some of the advanced operations are more complex to implement; others are no more complex, but are of interest to a small minority of MAPI components.</span></span> 
  
<span data-ttu-id="2c09e-112">更常见操作包括：</span><span class="sxs-lookup"><span data-stu-id="2c09e-112">The more common operations are:</span></span>
  
- <span data-ttu-id="2c09e-113">列操作影响单个列。</span><span class="sxs-lookup"><span data-stu-id="2c09e-113">Column operations, which affect single columns.</span></span> <span data-ttu-id="2c09e-114">包括指定要包含在列集和在其中他们应包含的顺序中的属性。</span><span class="sxs-lookup"><span data-stu-id="2c09e-114">These include specifying the properties to be included in the column set and the order in which they should be included.</span></span>
    
- <span data-ttu-id="2c09e-115">行操作会影响单个行。</span><span class="sxs-lookup"><span data-stu-id="2c09e-115">Row operations, which affect single rows.</span></span> <span data-ttu-id="2c09e-116">数据检索和维护操作包括： 添加、 删除和修改单个一行或多行。</span><span class="sxs-lookup"><span data-stu-id="2c09e-116">These include data retrieval and the maintenance operations: adding, deleting, and modifying a single row or rows.</span></span>
    
- <span data-ttu-id="2c09e-117">全局操作，影响整个表格。</span><span class="sxs-lookup"><span data-stu-id="2c09e-117">Global operations, which affect the entire table.</span></span> <span data-ttu-id="2c09e-118">包括事件通知，搜索和排序。</span><span class="sxs-lookup"><span data-stu-id="2c09e-118">These include event notification, searching and sorting.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2c09e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c09e-119">See also</span></span>



[<span data-ttu-id="2c09e-120">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="2c09e-120">MAPI Tables</span></span>](mapi-tables.md)

