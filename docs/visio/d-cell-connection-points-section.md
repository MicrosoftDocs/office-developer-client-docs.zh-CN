---
title: D 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm205
localization_priority: Normal
ms.assetid: 28b18e8d-fecf-a798-813e-c1a310002244
description: 可用于输入或测试公式的草稿单元格。
ms.openlocfilehash: e7bd61b8bc7a1a3b765af738681d958e2c83ba05
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408171"
---
# <a name="d-cell-connection-points-section"></a><span data-ttu-id="c1a77-103">D 单元格（“Connection Points”内容）</span><span class="sxs-lookup"><span data-stu-id="c1a77-103">D Cell (Connection Points Section)</span></span>

<span data-ttu-id="c1a77-104">一种草稿单元格，可用于输入或测试公式。</span><span class="sxs-lookup"><span data-stu-id="c1a77-104">A scratch cell that you can use for entering or testing formulas.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c1a77-105">备注</span><span class="sxs-lookup"><span data-stu-id="c1a77-105">Remarks</span></span>

<span data-ttu-id="c1a77-106">若要访问 D 单元格，可右击一行，然后单击快捷菜单上的 **“更改行类型”**。</span><span class="sxs-lookup"><span data-stu-id="c1a77-106">To access the D cell, right-click a row, and then click **Change Row Type** on the shortcut menu.</span></span> 
  
<span data-ttu-id="c1a77-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 D 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c1a77-107">To get a reference to the D cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c1a77-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c1a77-108">Cell name:</span></span>  <br/> | <span data-ttu-id="c1a77-109">Connections.D[  *i*  ] 其中  *i*  = <1> 2， 3...</span><span class="sxs-lookup"><span data-stu-id="c1a77-109">Connections.D[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="c1a77-110">要从某个程序按索引获取对 D 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c1a77-110">To get a reference to the D cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c1a77-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c1a77-111">Section index:</span></span>  <br/> |<span data-ttu-id="c1a77-112">**visSectionConnectionPts**</span><span class="sxs-lookup"><span data-stu-id="c1a77-112">**visSectionConnectionPts**</span></span> <br/> |
| <span data-ttu-id="c1a77-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="c1a77-113">Row index:</span></span>  <br/> |<span data-ttu-id="c1a77-114">**visRowConnectionPts**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="c1a77-114">**visRowConnectionPts** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="c1a77-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c1a77-115">Cell index:</span></span>  <br/> |<span data-ttu-id="c1a77-116">**visCnnctD**</span><span class="sxs-lookup"><span data-stu-id="c1a77-116">**visCnnctD**</span></span> <br/> |
   

