---
title: Prompt 单元格（“User-Defined Cells”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm840
localization_priority: Normal
ms.assetid: d0f91e7d-2373-cfef-e105-fb17e77c7f2d
description: 指定关于为用户定义的单元格的说明性提示或注释。 应用程序自动将提示文本放在引号 () 以指示它是文本字符串。 如果键入等号 (=) 且省略引号，则可以在该单元格中输入应用程序求值的公式。
ms.openlocfilehash: 7684025e03bd3f4f68893179b1df00cc0cb535e2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435724"
---
# <a name="prompt-cell-user-defined-cells-section"></a><span data-ttu-id="cf166-105">Prompt 单元格（“User-Defined Cells”内容）</span><span class="sxs-lookup"><span data-stu-id="cf166-105">Prompt Cell (User-Defined Cells Section)</span></span>

<span data-ttu-id="cf166-p102">指定关于为用户定义的单元格的说明性提示或注释。应用程序自动将提示文本用引号 (" ") 引起来，以表示它是文本字符串。如果键入等号 (=) 且省略引号，则可以在该单元格中输入应用程序求值的公式。</span><span class="sxs-lookup"><span data-stu-id="cf166-p102">Specifies a descriptive prompt or comment for the user-defined cell. The application automatically encloses the prompt text in quotation marks (" ") to indicate that it is a text string. If you type an equal sign (=) and omit the quotation marks, you can enter a formula in this cell that the application evaluates.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="cf166-109">备注</span><span class="sxs-lookup"><span data-stu-id="cf166-109">Remarks</span></span>

<span data-ttu-id="cf166-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Prompt 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="cf166-110">To get a reference to the Prompt cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cf166-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cf166-111">Cell name:</span></span>  <br/> | <span data-ttu-id="cf166-112">用户。</span><span class="sxs-lookup"><span data-stu-id="cf166-112">User.</span></span>  <span data-ttu-id="cf166-113">*名称*  。提示用户。</span><span class="sxs-lookup"><span data-stu-id="cf166-113">*Name*  .Prompt            where User.</span></span>  <span data-ttu-id="cf166-114">*Name*  是行名称</span><span class="sxs-lookup"><span data-stu-id="cf166-114">*Name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="cf166-115">要从某个程序按索引获取对 Prompt 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="cf166-115">To get a reference to the Prompt cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cf166-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cf166-116">Section index:</span></span>  <br/> |<span data-ttu-id="cf166-117">**visSectionUser**</span><span class="sxs-lookup"><span data-stu-id="cf166-117">**visSectionUser**</span></span> <br/> |
| <span data-ttu-id="cf166-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="cf166-118">Row index:</span></span>  <br/> |<span data-ttu-id="cf166-119">**visRowUser +** *i*            其中  *i*  = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="cf166-119">**visRowUser +** *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="cf166-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cf166-120">Cell index:</span></span>  <br/> |<span data-ttu-id="cf166-121">**visUserPrompt**</span><span class="sxs-lookup"><span data-stu-id="cf166-121">**visUserPrompt**</span></span> <br/> |
   

