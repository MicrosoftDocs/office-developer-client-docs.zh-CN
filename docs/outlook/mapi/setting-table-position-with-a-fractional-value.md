---
title: 使用分数值设置表位置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 80d31611-e508-4b17-b482-bedf76db26ff
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7800a58cad7b4e2b0b1696706c8e1d401ed424d7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339261"
---
# <a name="setting-table-position-with-a-fractional-value"></a><span data-ttu-id="86c1c-103">使用分数值设置表位置</span><span class="sxs-lookup"><span data-stu-id="86c1c-103">Setting Table Position with a Fractional Value</span></span>

  
  
<span data-ttu-id="86c1c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="86c1c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="86c1c-105">表用户可以移动到表示相对于总数的大概百分比的行的位置。</span><span class="sxs-lookup"><span data-stu-id="86c1c-105">Table users can move to a position that represents an approximate percentage of rows in relation to the total.</span></span> <span data-ttu-id="86c1c-106">这种定位方法将表分成多个部分, 而不是移到确切的行。</span><span class="sxs-lookup"><span data-stu-id="86c1c-106">Rather than moving to an exact row, this method of positioning divides the table into portions based on fractions.</span></span> <span data-ttu-id="86c1c-107">例如, 表用户可以移动到表的半角点, 或者移动到表中的7/8 行。</span><span class="sxs-lookup"><span data-stu-id="86c1c-107">Table users can move, for example, to a table's half-way point or to the row that is 7/8 of the way through the table.</span></span> 
  
 <span data-ttu-id="86c1c-108">**将游标移动大约行数**</span><span class="sxs-lookup"><span data-stu-id="86c1c-108">**To move the cursor an approximate number of rows**</span></span>
  
- <span data-ttu-id="86c1c-109">调用[IMAPITable:: SeekRowApprox](imapitable-seekrowapprox.md)。</span><span class="sxs-lookup"><span data-stu-id="86c1c-109">Call [IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md).</span></span> <span data-ttu-id="86c1c-110">**SeekRowApprox**移动到表示特定百分比的行 (相对于表的开头) 的行。</span><span class="sxs-lookup"><span data-stu-id="86c1c-110">**SeekRowApprox** moves to the row that represents a particular percentage of rows in relation to the beginning of the table.</span></span> <span data-ttu-id="86c1c-111">此百分比在_ulNumerator_和_ulDenominator_参数中指定。</span><span class="sxs-lookup"><span data-stu-id="86c1c-111">This percentage is specified in the  _ulNumerator_ and  _ulDenominator_ parameters.</span></span> <span data-ttu-id="86c1c-112">**SeekRowApprox**经常用于实现滚动条。</span><span class="sxs-lookup"><span data-stu-id="86c1c-112">**SeekRowApprox** is used frequently to implement scroll bars.</span></span> 
    
 <span data-ttu-id="86c1c-113">**确定表的大概位置**</span><span class="sxs-lookup"><span data-stu-id="86c1c-113">**To determine a table's approximate position**</span></span>
  
- <span data-ttu-id="86c1c-114">调用[IMAPITable:: QueryPosition](imapitable-queryposition.md)。</span><span class="sxs-lookup"><span data-stu-id="86c1c-114">Call [IMAPITable::QueryPosition](imapitable-queryposition.md).</span></span> <span data-ttu-id="86c1c-115">**QueryPosition**可用于通知用户当前位置。</span><span class="sxs-lookup"><span data-stu-id="86c1c-115">**QueryPosition** can be used to inform the user of the current position.</span></span> <span data-ttu-id="86c1c-116">它根据表中的行数和当前行数设置一个小数值。</span><span class="sxs-lookup"><span data-stu-id="86c1c-116">It sets a fractional value based on the number of rows in the table and the number of the current row.</span></span> <span data-ttu-id="86c1c-117">预期此值表示近似值。</span><span class="sxs-lookup"><span data-stu-id="86c1c-117">Expect that this value represents an approximation.</span></span> <span data-ttu-id="86c1c-118">建议不要将表实施者计算出确切的位置, 因为准确的实现可能会导致调用开销较高, 尤其是在分类表上。</span><span class="sxs-lookup"><span data-stu-id="86c1c-118">Table implementers are encouraged not to calculate the exact position because accurate implementations can be expensive to invoke, especially on categorized tables.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="86c1c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86c1c-119">See also</span></span>



[<span data-ttu-id="86c1c-120">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="86c1c-120">MAPI Tables</span></span>](mapi-tables.md)

