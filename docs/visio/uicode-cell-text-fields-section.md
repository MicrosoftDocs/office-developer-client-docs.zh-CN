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
ms.openlocfilehash: 293451b61def59ccfdf849dc597def9521fd22e5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422213"
---
# <a name="uicode-cell-text-fields-section"></a><span data-ttu-id="d031a-103">UICode 单元格（“Text Fields”内容）</span><span class="sxs-lookup"><span data-stu-id="d031a-103">UICode Cell (Text Fields Section)</span></span>

<span data-ttu-id="d031a-104">确定在早于 Visio 2000 的 Visio 版本中插入的域的代码。</span><span class="sxs-lookup"><span data-stu-id="d031a-104">Determines the code of an inserted field in versions of Visio earlier than Visio 2000.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d031a-105">说明</span><span class="sxs-lookup"><span data-stu-id="d031a-105">Remarks</span></span>

<span data-ttu-id="d031a-p101">此单元格不显示在 ShapeSheet 窗口中。如果需要处理向后兼容问题，例如以 Visio 5.0 版文件格式保存 Visio 2000 版绘图，则使用此单元格。</span><span class="sxs-lookup"><span data-stu-id="d031a-p101">This cell does not appear in the ShapeSheet window. Use this cell if you need to deal with backward capability issues, such as saving a Visio version 2000 drawing in Visio version 5.0 file format.</span></span>
  
<span data-ttu-id="d031a-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 UICode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d031a-108">To get a reference to the UICode cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d031a-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d031a-109">Cell name:</span></span>  <br/> | <span data-ttu-id="d031a-110">UICod [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="d031a-110">Fields.UICod[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="d031a-111">要从某个程序按索引获取对 UICode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d031a-111">To get a reference to the UICode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d031a-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d031a-112">Section index:</span></span>  <br/> |<span data-ttu-id="d031a-113">**visSectionTextField**</span><span class="sxs-lookup"><span data-stu-id="d031a-113">**visSectionTextField**</span></span> <br/> |
| <span data-ttu-id="d031a-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="d031a-114">Row index:</span></span>  <br/> |<span data-ttu-id="d031a-115">**visRowField** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="d031a-115">**visRowField** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="d031a-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d031a-116">Cell index:</span></span>  <br/> |<span data-ttu-id="d031a-117">**visFieldUICode**</span><span class="sxs-lookup"><span data-stu-id="d031a-117">**visFieldUICode**</span></span> <br/> |
   

