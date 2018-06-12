---
title: 设置表的分数的值的位置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 80d31611-e508-4b17-b482-bedf76db26ff
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 104de38a41408091a6fbb69995de4f41f6fea6a2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778763"
---
# <a name="setting-table-position-with-a-fractional-value"></a><span data-ttu-id="bbe5e-103">设置表的分数的值的位置</span><span class="sxs-lookup"><span data-stu-id="bbe5e-103">Setting Table Position with a Fractional Value</span></span>

  
  
<span data-ttu-id="bbe5e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bbe5e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bbe5e-105">表用户可以移动到值，该值代表大概所占比例相对于总计行的位置。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-105">Table users can move to a position that represents an approximate percentage of rows in relation to the total.</span></span> <span data-ttu-id="bbe5e-106">而不是移动到精确的行，此方法的定位除以成几部分表基于分数。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-106">Rather than moving to an exact row, this method of positioning divides the table into portions based on fractions.</span></span> <span data-ttu-id="bbe5e-107">表用户可以移动，例如，到表的一半点或为 7/8 通过表的方式的行。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-107">Table users can move, for example, to a table's half-way point or to the row that is 7/8 of the way through the table.</span></span> 
  
 <span data-ttu-id="bbe5e-108">**将光标近似行数**</span><span class="sxs-lookup"><span data-stu-id="bbe5e-108">**To move the cursor an approximate number of rows**</span></span>
  
- <span data-ttu-id="bbe5e-109">调用[IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md)。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-109">Call [IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md).</span></span> <span data-ttu-id="bbe5e-110">**SeekRowApprox**将移至表示特定所占比例相对开始于 table 的行的行。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-110">**SeekRowApprox** moves to the row that represents a particular percentage of rows in relation to the beginning of the table.</span></span> <span data-ttu-id="bbe5e-111">在_ulNumerator_和_ulDenominator_参数中指定此百分比。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-111">This percentage is specified in the  _ulNumerator_ and  _ulDenominator_ parameters.</span></span> <span data-ttu-id="bbe5e-112">**SeekRowApprox**经常用于实现滚动条。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-112">**SeekRowApprox** is used frequently to implement scroll bars.</span></span> 
    
 <span data-ttu-id="bbe5e-113">**若要确定表的大概位置**</span><span class="sxs-lookup"><span data-stu-id="bbe5e-113">**To determine a table's approximate position**</span></span>
  
- <span data-ttu-id="bbe5e-114">调用[IMAPITable::QueryPosition](imapitable-queryposition.md)。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-114">Call [IMAPITable::QueryPosition](imapitable-queryposition.md).</span></span> <span data-ttu-id="bbe5e-115">**QueryPosition**可用于通知的用户的当前位置。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-115">**QueryPosition** can be used to inform the user of the current position.</span></span> <span data-ttu-id="bbe5e-116">设置基于的表中的行数和当前行数的小数值。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-116">It sets a fractional value based on the number of rows in the table and the number of the current row.</span></span> <span data-ttu-id="bbe5e-117">希望此值表示近似值。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-117">Expect that this value represents an approximation.</span></span> <span data-ttu-id="bbe5e-118">鼓励不计算确切的位置，因为准确实现成本很高调用，尤其是在分类表上将表实施。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-118">Table implementers are encouraged not to calculate the exact position because accurate implementations can be expensive to invoke, especially on categorized tables.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="bbe5e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbe5e-119">See also</span></span>



[<span data-ttu-id="bbe5e-120">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="bbe5e-120">MAPI Tables</span></span>](mapi-tables.md)

