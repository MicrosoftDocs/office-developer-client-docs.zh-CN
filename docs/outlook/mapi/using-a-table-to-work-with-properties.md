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
# <a name="using-a-table-to-work-with-properties"></a><span data-ttu-id="d3538-103">使用表处理属性</span><span class="sxs-lookup"><span data-stu-id="d3538-103">Using a Table to Work with Properties</span></span>

  
  
<span data-ttu-id="d3538-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d3538-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d3538-105">许多属性都可从支持它们的对象和表中的列使用。</span><span class="sxs-lookup"><span data-stu-id="d3538-105">Many properties are available both from the objects that support them and as columns on tables.</span></span> <span data-ttu-id="d3538-106">只要有可能, 请通过表检索这些属性。</span><span class="sxs-lookup"><span data-stu-id="d3538-106">Whenever possible, retrieve these properties through the table.</span></span>
  
<span data-ttu-id="d3538-107">调用[IMAPITable:: SetColumns](imapitable-setcolumns.md)以包含客户端所需的所有属性和[IMAPITable:: QueryRows](imapitable-queryrows.md)检索表的所有行。</span><span class="sxs-lookup"><span data-stu-id="d3538-107">Call [IMAPITable::SetColumns](imapitable-setcolumns.md) to include all of the properties that your client needs and [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve all of the rows of the table.</span></span> 
  
<span data-ttu-id="d3538-108">这两个呼叫通常足以检索足够的信息以向用户显示, 并且经常需要进行任何必要的内部处理, 从而调用**OpenEntry**以打开不必要的对象。</span><span class="sxs-lookup"><span data-stu-id="d3538-108">These two calls are usually sufficient for retrieving enough information to display to a user, and are frequently sufficient for any necessary internal processing, making a call to **OpenEntry** to open the object unnecessary.</span></span> 
  
<span data-ttu-id="d3538-109">只有两个例外:</span><span class="sxs-lookup"><span data-stu-id="d3538-109">There are only two exceptions:</span></span>
  
- <span data-ttu-id="d3538-110">如果该属性超过255个字节。</span><span class="sxs-lookup"><span data-stu-id="d3538-110">If the property is over 255 bytes.</span></span> <span data-ttu-id="d3538-111">\* \* IMAPITable \* \* 接口可能不会返回整个属性值, 而是将其截断为255字节。</span><span class="sxs-lookup"><span data-stu-id="d3538-111">The \*\* IMAPITable \*\* interface might not return the entire property value, instead truncating it at 255 bytes.</span></span> <span data-ttu-id="d3538-112">不过, 请考虑这种折衷。</span><span class="sxs-lookup"><span data-stu-id="d3538-112">Think about this tradeoff, though.</span></span> <span data-ttu-id="d3538-113">如果要向用户显示此数据, 则255字节可能足以满足文本字段 (如注释) 的需要。</span><span class="sxs-lookup"><span data-stu-id="d3538-113">If you are displaying this data to the user, 255 bytes may be enough for a textual field such as a comment.</span></span> 
    
- <span data-ttu-id="d3538-114">如果需要表中单个行的特定属性。</span><span class="sxs-lookup"><span data-stu-id="d3538-114">If you need a specific property from a single row in a table.</span></span> <span data-ttu-id="d3538-115">在这种情况下, 不需要创建包含永远不使用的属性的表。</span><span class="sxs-lookup"><span data-stu-id="d3538-115">In this case it is unnecessary to create a table with properties that will never be used.</span></span> <span data-ttu-id="d3538-116">大多数时候, 所有行都需要相同的属性。</span><span class="sxs-lookup"><span data-stu-id="d3538-116">Most of the time you will need the same properties for all rows.</span></span>
    

