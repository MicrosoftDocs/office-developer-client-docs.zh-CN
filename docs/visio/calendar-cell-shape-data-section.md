---
title: Calendar 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60027
localization_priority: Normal
ms.assetid: f5dcc6d9-474a-9ecb-21f5-56415d934890
description: 确定当数据类型为日期时用于形状数据的日历。
ms.openlocfilehash: 502ecd8a028c4c0d9841bbd3e0ed369f73bd6b65
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779814"
---
# <a name="calendar-cell-shape-data-section"></a><span data-ttu-id="061c7-103">Calendar 单元格（“Shape Data”内容）</span><span class="sxs-lookup"><span data-stu-id="061c7-103">Calendar Cell (Shape Data Section)</span></span>

<span data-ttu-id="061c7-104">确定当数据类型为日期时用于形状数据的日历。</span><span class="sxs-lookup"><span data-stu-id="061c7-104">Determines the calendar that is used for shape data when the data type is Date.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="061c7-105">注释</span><span class="sxs-lookup"><span data-stu-id="061c7-105">Remarks</span></span>

<span data-ttu-id="061c7-106">可能的值为：0（公历）、1（阿拉伯回历）、2（希伯来农历）、3（台历）、4（日本年号）、5（泰国佛历）、6（朝鲜檀纪历）、7（萨卡时代日历）、8（英语转译）和 9（法语转译）。</span><span class="sxs-lookup"><span data-stu-id="061c7-106">The possible values are: 0 (Western), 1 (Arabic Hijri), 2 (Hebrew Lunar), 3 (Taiwan Calendar), 4 (Japanese Emperor Reign), 5 (Thai Buddhist), 6 (Korean Danki), 7 (Saka Era), 8 (English transliterated), and 9 (French transliterated ).</span></span> 
  
<span data-ttu-id="061c7-107">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Calendar 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="061c7-107">To get a reference to the Calendar cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="061c7-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="061c7-108">Cell name:</span></span>  <br/> | <span data-ttu-id="061c7-109">属性。 *名称*。日历其中属性。 *name*是行名称</span><span class="sxs-lookup"><span data-stu-id="061c7-109">Prop.  *name*  .Calendar            where Prop.  *name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="061c7-110">若要从某个程序按索引获取对 Calendar 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="061c7-110">To get a reference to the Calendar cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="061c7-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="061c7-111">Section index:</span></span>  <br/> |<span data-ttu-id="061c7-112">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="061c7-112">**visSectionProp**</span></span> <br/> |
| <span data-ttu-id="061c7-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="061c7-113">Row index:</span></span>  <br/> |<span data-ttu-id="061c7-114">**visRowProp** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="061c7-114">**visRowProp** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="061c7-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="061c7-115">Cell index:</span></span>  <br/> |<span data-ttu-id="061c7-116">**visCustPropsCalendar**</span><span class="sxs-lookup"><span data-stu-id="061c7-116">**visCustPropsCalendar**</span></span> <br/> |
   

