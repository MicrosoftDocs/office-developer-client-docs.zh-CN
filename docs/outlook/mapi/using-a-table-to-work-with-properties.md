---
title: 使用表处理属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c18ed9f7-c053-4453-b0b1-06234cdfb025
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e4e7ecda40f3f3fcb05700ba3e8b79ab21cbe35b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779058"
---
# <a name="using-a-table-to-work-with-properties"></a><span data-ttu-id="e95e2-103">使用表处理属性</span><span class="sxs-lookup"><span data-stu-id="e95e2-103">Using a Table to Work with Properties</span></span>

  
  
<span data-ttu-id="e95e2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e95e2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e95e2-105">从支持它们的对象和作为对表的列都提供了许多属性。</span><span class="sxs-lookup"><span data-stu-id="e95e2-105">Many properties are available both from the objects that support them and as columns on tables.</span></span> <span data-ttu-id="e95e2-106">只要有可能，检索表通过这些属性。</span><span class="sxs-lookup"><span data-stu-id="e95e2-106">Whenever possible, retrieve these properties through the table.</span></span>
  
<span data-ttu-id="e95e2-107">呼叫[IMAPITable::SetColumns](imapitable-setcolumns.md)要包含的所有客户端所需的属性和[IMAPITable::QueryRows](imapitable-queryrows.md)检索所有表的行。</span><span class="sxs-lookup"><span data-stu-id="e95e2-107">Call [IMAPITable::SetColumns](imapitable-setcolumns.md) to include all of the properties that your client needs and [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve all of the rows of the table.</span></span> 
  
<span data-ttu-id="e95e2-108">以下两个通话通常足以满足检索足够的信息来显示给用户，且经常足以进行任何所需的内部处理，调用**OpenEntry**打开不必要的对象。</span><span class="sxs-lookup"><span data-stu-id="e95e2-108">These two calls are usually sufficient for retrieving enough information to display to a user, and are frequently sufficient for any necessary internal processing, making a call to **OpenEntry** to open the object unnecessary.</span></span> 
  
<span data-ttu-id="e95e2-109">有只有两个例外情况：</span><span class="sxs-lookup"><span data-stu-id="e95e2-109">There are only two exceptions:</span></span>
  
- <span data-ttu-id="e95e2-110">如果属性为超过 255 个字节。</span><span class="sxs-lookup"><span data-stu-id="e95e2-110">If the property is over 255 bytes.</span></span> <span data-ttu-id="e95e2-111">* * IMAPITable * * 界面可能不会返回整个属性值，而将其截断在 255 个字节。</span><span class="sxs-lookup"><span data-stu-id="e95e2-111">The ** IMAPITable ** interface might not return the entire property value, instead truncating it at 255 bytes.</span></span> <span data-ttu-id="e95e2-112">上述考虑此利弊权衡。</span><span class="sxs-lookup"><span data-stu-id="e95e2-112">Think about this tradeoff, though.</span></span> <span data-ttu-id="e95e2-113">如果您要向用户显示该数据，255 个字节可能足够如注释的文本字段。</span><span class="sxs-lookup"><span data-stu-id="e95e2-113">If you are displaying this data to the user, 255 bytes may be enough for a textual field such as a comment.</span></span> 
    
- <span data-ttu-id="e95e2-114">如果您需要从表中的单个行的特定属性。</span><span class="sxs-lookup"><span data-stu-id="e95e2-114">If you need a specific property from a single row in a table.</span></span> <span data-ttu-id="e95e2-115">在这种情况下不需要创建一个包含永远不会将使用的属性表。</span><span class="sxs-lookup"><span data-stu-id="e95e2-115">In this case it is unnecessary to create a table with properties that will never be used.</span></span> <span data-ttu-id="e95e2-116">大多数情况下需要将相同的属性的所有行。</span><span class="sxs-lookup"><span data-stu-id="e95e2-116">Most of the time you will need the same properties for all rows.</span></span>
    

