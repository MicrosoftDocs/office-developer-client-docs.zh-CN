---
title: Calendar 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60029
localization_priority: Normal
ms.assetid: 0c3e275e-25f0-3681-03f4-257145c19690
description: 确定当数据类型为日期时用于文本字段的日历。
ms.openlocfilehash: e90f757fb176375c8f9e9d5744e09b67afaca527
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424749"
---
# <a name="calendar-cell-text-fields-section"></a><span data-ttu-id="b4e63-103">Calendar 单元格（“Text Fields”内容）</span><span class="sxs-lookup"><span data-stu-id="b4e63-103">Calendar Cell (Text Fields Section)</span></span>

<span data-ttu-id="b4e63-104">确定当数据类型为日期时用于文本字段的日历。</span><span class="sxs-lookup"><span data-stu-id="b4e63-104">Determines the calendar that is used for a text field when the data type is Date.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b4e63-105">说明</span><span class="sxs-lookup"><span data-stu-id="b4e63-105">Remarks</span></span>

<span data-ttu-id="b4e63-106">可能的值为：0（公历）、1（阿拉伯回历）、2（希伯来农历）、3（台历）、4（日本年号）、5（泰国佛历）、6（朝鲜檀纪历）、7（萨卡时代日历）、8（英语转译）和 9（法语转译）。</span><span class="sxs-lookup"><span data-stu-id="b4e63-106">The possible values are: 0 (Western), 1 (Arabic Hijri), 2 (Hebrew Lunar), 3 (Taiwan Calendar), 4 (Japanese Emperor Reign), 5 (Thai Buddhist), 6 (Korean Danki), 7 (Saka Era), 8 (English transliterated), and 9 (French transliterated ).</span></span> 
  
<span data-ttu-id="b4e63-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Calendar 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="b4e63-107">To get a reference to the Calendar cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b4e63-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b4e63-108">Cell name:</span></span>  <br/> | <span data-ttu-id="b4e63-109">字段。日历 [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="b4e63-109">Fields.Calendar[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="b4e63-110">要从某个程序按索引获取对 Calendar 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="b4e63-110">To get a reference to the Calendar cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b4e63-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b4e63-111">Section index:</span></span>  <br/> |<span data-ttu-id="b4e63-112">**visSectionTextField**</span><span class="sxs-lookup"><span data-stu-id="b4e63-112">**visSectionTextField**</span></span> <br/> |
| <span data-ttu-id="b4e63-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="b4e63-113">Row index:</span></span>  <br/> |<span data-ttu-id="b4e63-114">**visRowField** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="b4e63-114">**visRowField** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="b4e63-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b4e63-115">Cell index:</span></span>  <br/> |<span data-ttu-id="b4e63-116">**visFieldCalendar**</span><span class="sxs-lookup"><span data-stu-id="b4e63-116">**visFieldCalendar**</span></span> <br/> |
   

