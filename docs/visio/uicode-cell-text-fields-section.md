---
title: UICode 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1075
localization_priority: Normal
ms.assetid: 1d9717c1-4310-0d62-874f-4df77cd81627
description: 确定在早于 Visio 2000 的 Visio 版本中插入的域的代码。
ms.openlocfilehash: ce05f779bfebd5720555f1a2d92b1f9f92cfbdfd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781586"
---
# <a name="uicode-cell-text-fields-section"></a><span data-ttu-id="b4b27-103">UICode 单元格（“Text Fields”内容）</span><span class="sxs-lookup"><span data-stu-id="b4b27-103">UICode Cell (Text Fields Section)</span></span>

<span data-ttu-id="b4b27-104">确定在早于 Visio 2000 的 Visio 版本中插入的域的代码。</span><span class="sxs-lookup"><span data-stu-id="b4b27-104">Determines the code of an inserted field in versions of Visio earlier than Visio 2000.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b4b27-105">注释</span><span class="sxs-lookup"><span data-stu-id="b4b27-105">Remarks</span></span>

<span data-ttu-id="b4b27-p101">此单元格不显示在 ShapeSheet 窗口中。如果需要处理向后兼容问题，例如以 Visio 5.0 版文件格式保存 Visio 2000 版绘图，则使用此单元格。</span><span class="sxs-lookup"><span data-stu-id="b4b27-p101">This cell does not appear in the ShapeSheet window. Use this cell if you need to deal with backward capability issues, such as saving a Visio version 2000 drawing in Visio version 5.0 file format.</span></span>
  
<span data-ttu-id="b4b27-108">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 UICode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="b4b27-108">To get a reference to the UICode cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b4b27-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b4b27-109">Cell name:</span></span>  <br/> | <span data-ttu-id="b4b27-110">Fields.UICod [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="b4b27-110">Fields.UICod[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="b4b27-111">若要从某个程序按索引获取对 UICode 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="b4b27-111">To get a reference to the UICode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b4b27-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b4b27-112">Section index:</span></span>  <br/> |<span data-ttu-id="b4b27-113">**visSectionTextField**</span><span class="sxs-lookup"><span data-stu-id="b4b27-113">**visSectionTextField**</span></span> <br/> |
| <span data-ttu-id="b4b27-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="b4b27-114">Row index:</span></span>  <br/> |<span data-ttu-id="b4b27-115">**visRowField** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="b4b27-115">**visRowField** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="b4b27-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b4b27-116">Cell index:</span></span>  <br/> |<span data-ttu-id="b4b27-117">**visFieldUICode**</span><span class="sxs-lookup"><span data-stu-id="b4b27-117">**visFieldUICode**</span></span> <br/> |
   

