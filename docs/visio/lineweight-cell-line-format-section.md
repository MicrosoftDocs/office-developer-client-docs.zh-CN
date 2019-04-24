---
title: LineWeight 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm585
localization_priority: Normal
ms.assetid: 16b0e293-eeef-34b4-aeb0-4472815dd543
description: 确定形状的线条粗细。 通过输入具有有效度量单位的数字即可设置线条粗细。
ms.openlocfilehash: 654a93f939226bedab2e40ab591dad0e3f872267
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341809"
---
# <a name="lineweight-cell-line-format-section"></a><span data-ttu-id="0ad22-104">LineWeight 单元格（“Line Format”内容）</span><span class="sxs-lookup"><span data-stu-id="0ad22-104">LineWeight Cell (Line Format Section)</span></span>

<span data-ttu-id="0ad22-105">确定形状的线条粗细。</span><span class="sxs-lookup"><span data-stu-id="0ad22-105">Determines the line weight of a shape.</span></span> <span data-ttu-id="0ad22-106">通过输入具有有效度量单位的数字即可设置线条粗细。</span><span class="sxs-lookup"><span data-stu-id="0ad22-106">Set the line weight by entering a number with a valid unit of measure.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0ad22-107">注解</span><span class="sxs-lookup"><span data-stu-id="0ad22-107">Remarks</span></span>

<span data-ttu-id="0ad22-108">还可以在 **“线条”** 对话框（在 **“开始”** 选项卡上，**“形状”** 组中，单击 **“线条”**，指向 **“权重”**，然后单击 **“其他线条”**）中设置 LineWeight 的值。</span><span class="sxs-lookup"><span data-stu-id="0ad22-108">You can also set the value of LineWeight in the **Line** dialog box (on the **Home** tab, in the **Shape** group, click **Line**, point to **Weight**, and then click **More Lines**).</span></span>
  
<span data-ttu-id="0ad22-109">如果未输入度量单位, 则使用在 " **Visio 选项**" 对话框中指定的文本的度量单位 (单击 "**文件**" 选项卡, 然后单击 "**选项**")。</span><span class="sxs-lookup"><span data-stu-id="0ad22-109">If the unit of measure is not entered, the unit of measure for text specified in the **Visio Options** dialog box is used (click the **File** tab, and then click **Options**).</span></span> <span data-ttu-id="0ad22-110">线条粗细与绘图比例无关。</span><span class="sxs-lookup"><span data-stu-id="0ad22-110">Line weight is independent of the scale of the drawing.</span></span> <span data-ttu-id="0ad22-111">即使绘图比例进行调整，线条粗细仍将保持不变。</span><span class="sxs-lookup"><span data-stu-id="0ad22-111">If the drawing is scaled, the line weight remains the same.</span></span> 
  
<span data-ttu-id="0ad22-112">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LineWeight 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="0ad22-112">To get a reference to the LineWeight cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0ad22-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="0ad22-113">Cell name:</span></span>  <br/> | <span data-ttu-id="0ad22-114">LineWeight</span><span class="sxs-lookup"><span data-stu-id="0ad22-114">LineWeight</span></span>  <br/> |
   
<span data-ttu-id="0ad22-115">若要从某个程序按索引获取对 LineWeight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="0ad22-115">To get a reference to the LineWeight cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0ad22-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="0ad22-116">Section index:</span></span>  <br/> |<span data-ttu-id="0ad22-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="0ad22-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="0ad22-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="0ad22-118">Row index:</span></span>  <br/> |<span data-ttu-id="0ad22-119">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="0ad22-119">**visRowLine**</span></span> <br/> |
| <span data-ttu-id="0ad22-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="0ad22-120">Cell index:</span></span>  <br/> |<span data-ttu-id="0ad22-121">**visLineWeight**</span><span class="sxs-lookup"><span data-stu-id="0ad22-121">**visLineWeight**</span></span> <br/> |
   

