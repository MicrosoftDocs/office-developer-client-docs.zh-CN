---
title: 使用小数值设置表位置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 80d31611-e508-4b17-b482-bedf76db26ff
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7800a58cad7b4e2b0b1696706c8e1d401ed424d7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437334"
---
# <a name="setting-table-position-with-a-fractional-value"></a><span data-ttu-id="7c9f8-103">使用小数值设置表位置</span><span class="sxs-lookup"><span data-stu-id="7c9f8-103">Setting Table Position with a Fractional Value</span></span>

  
  
<span data-ttu-id="7c9f8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7c9f8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7c9f8-105">表格用户可以移动到表示行占总行的大致百分比的位置。</span><span class="sxs-lookup"><span data-stu-id="7c9f8-105">Table users can move to a position that represents an approximate percentage of rows in relation to the total.</span></span> <span data-ttu-id="7c9f8-106">这种定位方法不是移动到精确行，而是根据分数将表格划分为多个部分。</span><span class="sxs-lookup"><span data-stu-id="7c9f8-106">Rather than moving to an exact row, this method of positioning divides the table into portions based on fractions.</span></span> <span data-ttu-id="7c9f8-107">例如，表格用户可以移动到表格的半向点或经过表格的 7/8 行。</span><span class="sxs-lookup"><span data-stu-id="7c9f8-107">Table users can move, for example, to a table's half-way point or to the row that is 7/8 of the way through the table.</span></span> 
  
 <span data-ttu-id="7c9f8-108">**将光标移动大致的行数**</span><span class="sxs-lookup"><span data-stu-id="7c9f8-108">**To move the cursor an approximate number of rows**</span></span>
  
- <span data-ttu-id="7c9f8-109">调用 [IMAPITable：：SeekRowApprox](imapitable-seekrowapprox.md)。</span><span class="sxs-lookup"><span data-stu-id="7c9f8-109">Call [IMAPITable::SeekRowApprox](imapitable-seekrowapprox.md).</span></span> <span data-ttu-id="7c9f8-110">**SeekRowApprox** 将移动到代表相对于表格开头的行的特定百分比的行。</span><span class="sxs-lookup"><span data-stu-id="7c9f8-110">**SeekRowApprox** moves to the row that represents a particular percentage of rows in relation to the beginning of the table.</span></span> <span data-ttu-id="7c9f8-111">此百分比在  _ulNumerator_ 和  _ulDenominator_ 参数中指定。</span><span class="sxs-lookup"><span data-stu-id="7c9f8-111">This percentage is specified in the  _ulNumerator_ and  _ulDenominator_ parameters.</span></span> <span data-ttu-id="7c9f8-112">**SeekRowApprox** 通常用于实现滚动条。</span><span class="sxs-lookup"><span data-stu-id="7c9f8-112">**SeekRowApprox** is used frequently to implement scroll bars.</span></span> 
    
 <span data-ttu-id="7c9f8-113">**确定表的近似位置**</span><span class="sxs-lookup"><span data-stu-id="7c9f8-113">**To determine a table's approximate position**</span></span>
  
- <span data-ttu-id="7c9f8-114">调用 [IMAPITable：：QueryPosition](imapitable-queryposition.md)。</span><span class="sxs-lookup"><span data-stu-id="7c9f8-114">Call [IMAPITable::QueryPosition](imapitable-queryposition.md).</span></span> <span data-ttu-id="7c9f8-115">**QueryPosition** 可用于通知用户当前位置。</span><span class="sxs-lookup"><span data-stu-id="7c9f8-115">**QueryPosition** can be used to inform the user of the current position.</span></span> <span data-ttu-id="7c9f8-116">它基于表格中的行数和当前行的行数设置小数值。</span><span class="sxs-lookup"><span data-stu-id="7c9f8-116">It sets a fractional value based on the number of rows in the table and the number of the current row.</span></span> <span data-ttu-id="7c9f8-117">预计此值表示近似值。</span><span class="sxs-lookup"><span data-stu-id="7c9f8-117">Expect that this value represents an approximation.</span></span> <span data-ttu-id="7c9f8-118">建议表实施者不要计算精确位置，因为调用准确的实现成本可能很高，尤其是在分类表上。</span><span class="sxs-lookup"><span data-stu-id="7c9f8-118">Table implementers are encouraged not to calculate the exact position because accurate implementations can be expensive to invoke, especially on categorized tables.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="7c9f8-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c9f8-119">See also</span></span>



[<span data-ttu-id="7c9f8-120">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="7c9f8-120">MAPI Tables</span></span>](mapi-tables.md)

