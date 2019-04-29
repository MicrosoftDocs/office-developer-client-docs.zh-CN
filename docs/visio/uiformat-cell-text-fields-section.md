---
title: UIFormat 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1080
localization_priority: Normal
ms.assetid: 0dddef20-c58e-2306-ab8e-6cac8e159f61
description: 确定在早于 Visio 2000 的 Visio 版本中插入的域的格式。
ms.openlocfilehash: 16cefc5f45d6b5f0f677e35bd5d0937d48fb2680
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426364"
---
# <a name="uiformat-cell-text-fields-section"></a><span data-ttu-id="f5e86-103">UIFormat 单元格（“Text Fields”内容）</span><span class="sxs-lookup"><span data-stu-id="f5e86-103">UIFormat Cell (Text Fields Section)</span></span>

<span data-ttu-id="f5e86-104">确定在早于 Visio 2000 的 Visio 版本中插入的域的格式。</span><span class="sxs-lookup"><span data-stu-id="f5e86-104">Determines the format of an inserted field in versions of Visio earlier than Visio 2000.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f5e86-105">说明</span><span class="sxs-lookup"><span data-stu-id="f5e86-105">Remarks</span></span>

<span data-ttu-id="f5e86-p101">此单元格不显示在 ShapeSheet 窗口中。如果需要处理向后兼容问题，例如以 Visio 5.0 版文件格式保存 Visio 2000 版绘图，则使用此单元格。</span><span class="sxs-lookup"><span data-stu-id="f5e86-p101">This cell does not appear in the ShapeSheet window. Use this cell if you need to deal with backward capability issues, such as saving a Visio version 2000 drawing in Visio version 5.0 file format.</span></span>
  
<span data-ttu-id="f5e86-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 UIFormat 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f5e86-108">To get a reference to the UIFormat cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f5e86-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f5e86-109">Cell name:</span></span>  <br/> | <span data-ttu-id="f5e86-110">UIFmt [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="f5e86-110">Fields.UIFmt[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="f5e86-111">要从某个程序按索引获取对 UIFormat 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f5e86-111">To get a reference to the UIFormat cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f5e86-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f5e86-112">Section index:</span></span>  <br/> |<span data-ttu-id="f5e86-113">**visSectionTextField**</span><span class="sxs-lookup"><span data-stu-id="f5e86-113">**visSectionTextField**</span></span> <br/> |
| <span data-ttu-id="f5e86-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="f5e86-114">Row index:</span></span>  <br/> |<span data-ttu-id="f5e86-115">**visRowField** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="f5e86-115">**visRowField** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="f5e86-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f5e86-116">Cell index:</span></span>  <br/> |<span data-ttu-id="f5e86-117">**visFieldUIFormat**</span><span class="sxs-lookup"><span data-stu-id="f5e86-117">**visFieldUIFormat**</span></span> <br/> |
   

