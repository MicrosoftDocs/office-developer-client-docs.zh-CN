---
title: UICategory 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1070
localization_priority: Normal
ms.assetid: 365f7005-ba34-2311-4c5c-16344962fc3f
description: 确定在早于 Visio 2000 的 Visio 版本中插入的域的类别。
ms.openlocfilehash: fc060ac1533732749d10e1855dc3841602051520
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781591"
---
# <a name="uicategory-cell-text-fields-section"></a><span data-ttu-id="8b650-103">UICategory 单元格（“Text Fields”部分）</span><span class="sxs-lookup"><span data-stu-id="8b650-103">UICategory Cell (Text Fields Section)</span></span>

<span data-ttu-id="8b650-104">确定在早于 Visio 2000 的 Visio 版本中插入的域的类别。</span><span class="sxs-lookup"><span data-stu-id="8b650-104">Determines the category of an inserted field in versions of Visio earlier than Visio 2000.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8b650-105">注释</span><span class="sxs-lookup"><span data-stu-id="8b650-105">Remarks</span></span>

<span data-ttu-id="8b650-p101">此单元格不显示在 ShapeSheet 窗口中。如果需要处理向后兼容问题，例如以 Visio 5.0 版文件格式保存 Visio 2000 版绘图，则使用此单元格。</span><span class="sxs-lookup"><span data-stu-id="8b650-p101">This cell does not appear in the ShapeSheet window. Use this cell if you need to deal with backward capability issues such as saving a Visio version 2000 drawing in Visio version 5.0 file format.</span></span>
  
<span data-ttu-id="8b650-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 UICategory 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8b650-108">To get a reference to the UICategory cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8b650-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8b650-109">Cell name:</span></span>  <br/> | <span data-ttu-id="8b650-110">Fields.UICat [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="8b650-110">Fields.UICat[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="8b650-111">要从某个程序按索引获取对 UICategory 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8b650-111">To get a reference to the UICategory cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8b650-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8b650-112">Section index:</span></span>  <br/> |<span data-ttu-id="8b650-113">**visSectionTextField**</span><span class="sxs-lookup"><span data-stu-id="8b650-113">**visSectionTextField**</span></span> <br/> |
| <span data-ttu-id="8b650-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="8b650-114">Row index:</span></span>  <br/> |<span data-ttu-id="8b650-115">**visRowField** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="8b650-115">**visRowField** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="8b650-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8b650-116">Cell index:</span></span>  <br/> |<span data-ttu-id="8b650-117">**visFieldUICategory**</span><span class="sxs-lookup"><span data-stu-id="8b650-117">**visFieldUICategory**</span></span> <br/> |
   

