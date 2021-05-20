---
title: 使用表处理属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c18ed9f7-c053-4453-b0b1-06234cdfb025
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 59196f136c422be912ac2460cbbd25d8bc2e3330
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439910"
---
# <a name="using-a-table-to-work-with-properties"></a><span data-ttu-id="6c373-103">使用表处理属性</span><span class="sxs-lookup"><span data-stu-id="6c373-103">Using a Table to Work with Properties</span></span>

  
  
<span data-ttu-id="6c373-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6c373-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6c373-105">许多属性都从支持这些属性的对象和表上的列提供。</span><span class="sxs-lookup"><span data-stu-id="6c373-105">Many properties are available both from the objects that support them and as columns on tables.</span></span> <span data-ttu-id="6c373-106">如果可能，请通过表检索这些属性。</span><span class="sxs-lookup"><span data-stu-id="6c373-106">Whenever possible, retrieve these properties through the table.</span></span>
  
<span data-ttu-id="6c373-107">调用 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 以包含客户端需要的所有属性，并调用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 检索表的所有行。</span><span class="sxs-lookup"><span data-stu-id="6c373-107">Call [IMAPITable::SetColumns](imapitable-setcolumns.md) to include all of the properties that your client needs and [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve all of the rows of the table.</span></span> 
  
<span data-ttu-id="6c373-108">这两个调用通常足以检索向用户显示的足够信息，并且通常足以用于任何必要的内部处理，因此调用 **OpenEntry** 以打开对象是不必要的。</span><span class="sxs-lookup"><span data-stu-id="6c373-108">These two calls are usually sufficient for retrieving enough information to display to a user, and are frequently sufficient for any necessary internal processing, making a call to **OpenEntry** to open the object unnecessary.</span></span> 
  
<span data-ttu-id="6c373-109">只有两个例外：</span><span class="sxs-lookup"><span data-stu-id="6c373-109">There are only two exceptions:</span></span>
  
- <span data-ttu-id="6c373-110">如果属性超过 255 字节。</span><span class="sxs-lookup"><span data-stu-id="6c373-110">If the property is over 255 bytes.</span></span> <span data-ttu-id="6c373-111">\*\* IMAPITable \*\* 接口可能不会返回整个属性值，而是以 255 字节为单位截断它。</span><span class="sxs-lookup"><span data-stu-id="6c373-111">The \*\* IMAPITable \*\* interface might not return the entire property value, instead truncating it at 255 bytes.</span></span> <span data-ttu-id="6c373-112">但是，考虑此权衡。</span><span class="sxs-lookup"><span data-stu-id="6c373-112">Think about this tradeoff, though.</span></span> <span data-ttu-id="6c373-113">如果要向用户显示此数据，则对于文本字段（如注释）来说，255 个字节可能就足够了。</span><span class="sxs-lookup"><span data-stu-id="6c373-113">If you are displaying this data to the user, 255 bytes may be enough for a textual field such as a comment.</span></span> 
    
- <span data-ttu-id="6c373-114">如果需要表中的单个行中的特定属性。</span><span class="sxs-lookup"><span data-stu-id="6c373-114">If you need a specific property from a single row in a table.</span></span> <span data-ttu-id="6c373-115">在这种情况下，不必创建具有永远不会使用的属性的表。</span><span class="sxs-lookup"><span data-stu-id="6c373-115">In this case it is unnecessary to create a table with properties that will never be used.</span></span> <span data-ttu-id="6c373-116">大多数情况下，需要所有行的相同属性。</span><span class="sxs-lookup"><span data-stu-id="6c373-116">Most of the time you will need the same properties for all rows.</span></span>
    

