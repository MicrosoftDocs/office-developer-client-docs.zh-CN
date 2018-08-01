---
title: Calendar 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60028
localization_priority: Normal
ms.assetid: 7406b46d-b42d-187c-70e8-123c4da7e781
description: 确定当单元格公式包含日期信息时所使用的日历。
ms.openlocfilehash: 2bca91fd2efc283bcc8f2c5037c4d81dd9bcffc5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779804"
---
# <a name="calendar-cell-miscellaneous-section"></a><span data-ttu-id="eba0f-103">Calendar 单元格（“Miscellaneous”部分）</span><span class="sxs-lookup"><span data-stu-id="eba0f-103">Calendar Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="eba0f-104">确定当单元格公式包含日期信息时所使用的日历。</span><span class="sxs-lookup"><span data-stu-id="eba0f-104">Determines the calendar that is used when a cell formula contains Date information.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="eba0f-105">注释</span><span class="sxs-lookup"><span data-stu-id="eba0f-105">Remarks</span></span>

<span data-ttu-id="eba0f-106">可能的值为：0（公历）、1（阿拉伯回历）、2（希伯来农历）、3（台历）、4（日本年号）、5（泰国佛历）、6（朝鲜檀纪历）、7（萨卡时代日历）、8（英语转译）和 9（法语转译）。</span><span class="sxs-lookup"><span data-stu-id="eba0f-106">The possible values are: 0 (Western), 1 (Arabic Hijri), 2 (Hebrew Lunar), 3 (Taiwan Calendar), 4 (Japanese Emperor Reign), 5 (Thai Buddhist), 6 (Korean Danki), 7 (Saka Era), 8 (English transliterated), and 9 (French transliterated ).</span></span> 
  
<span data-ttu-id="eba0f-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Calendar 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="eba0f-107">To get a reference to the Calendar cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="eba0f-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="eba0f-108">Cell name:</span></span>  <br/> | <span data-ttu-id="eba0f-109">Calendar</span><span class="sxs-lookup"><span data-stu-id="eba0f-109">Calendar</span></span>  <br/> |
   
<span data-ttu-id="eba0f-110">若要从某个程序按索引获取对 Calendar 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="eba0f-110">To get a reference to the Calendar cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="eba0f-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="eba0f-111">Section index:</span></span>  <br/> |<span data-ttu-id="eba0f-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="eba0f-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="eba0f-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="eba0f-113">Row index:</span></span>  <br/> |<span data-ttu-id="eba0f-114">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="eba0f-114">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="eba0f-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="eba0f-115">Cell index:</span></span>  <br/> |<span data-ttu-id="eba0f-116">**visObjCalendar**</span><span class="sxs-lookup"><span data-stu-id="eba0f-116">**visObjCalendar**</span></span> <br/> |
   

