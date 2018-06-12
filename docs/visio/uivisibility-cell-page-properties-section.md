---
title: UIVisibility 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60090
localization_priority: Normal
ms.assetid: df7f79df-770a-4868-e7e2-05c3828e23eb
description: 确定用户界面 (UI) 中是否显示页名称。
ms.openlocfilehash: dcb4a14ff89c7f5c77916e6b188aaf87e1711ab0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781611"
---
# <a name="uivisibility-cell-page-properties-section"></a><span data-ttu-id="e77b6-103">UIVisibility 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="e77b6-103">UIVisibility Cell (Page Properties Section)</span></span>

<span data-ttu-id="e77b6-104">确定用户界面 (UI) 中是否显示页名称。</span><span class="sxs-lookup"><span data-stu-id="e77b6-104">Determines whether the page name is exposed in the user interface (UI).</span></span>
  
|<span data-ttu-id="e77b6-105">**值**</span><span class="sxs-lookup"><span data-stu-id="e77b6-105">**Value**</span></span>|<span data-ttu-id="e77b6-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="e77b6-106">**Description**</span></span>|<span data-ttu-id="e77b6-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="e77b6-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e77b6-108">0</span><span class="sxs-lookup"><span data-stu-id="e77b6-108">0</span></span>  <br/> |<span data-ttu-id="e77b6-109">在 UI 中显示页名称（默认值）。</span><span class="sxs-lookup"><span data-stu-id="e77b6-109">Display the page name in the UI (the default).</span></span>  <br/> |<span data-ttu-id="e77b6-110">**visUIVNormal**</span><span class="sxs-lookup"><span data-stu-id="e77b6-110">**visUIVNormal**</span></span> <br/> |
|<span data-ttu-id="e77b6-111">1</span><span class="sxs-lookup"><span data-stu-id="e77b6-111">1</span></span>  <br/> |<span data-ttu-id="e77b6-112">在 UI 中不显示页名称。</span><span class="sxs-lookup"><span data-stu-id="e77b6-112">Do not display the page name in the UI.</span></span>  <br/> |<span data-ttu-id="e77b6-113">**visUIVHidden**</span><span class="sxs-lookup"><span data-stu-id="e77b6-113">**visUIVHidden**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e77b6-114">备注</span><span class="sxs-lookup"><span data-stu-id="e77b6-114">Remarks</span></span>

<span data-ttu-id="e77b6-115">将 UIVisibility 单元格设置为**visUIVHidden**可防止页包含页面名称的字符串的显示位置在 UI 中任意位置显示。</span><span class="sxs-lookup"><span data-stu-id="e77b6-115">Setting the UIVisibility cell to **visUIVHidden** prevents the page from appearing anywhere in the UI where the string containing the page name appears.</span></span> <span data-ttu-id="e77b6-116">例如，页上不会列为**绘图资源管理器**中或在页面选项卡上的选项。</span><span class="sxs-lookup"><span data-stu-id="e77b6-116">For example, the page would not be listed as an option in the **Drawing Explorer** or on the page tabs.</span></span> <span data-ttu-id="e77b6-117">页面仍然可以访问，但是，如果您使用自动化或 UI 不包括页名称，例如，**打印**命令的路径。</span><span class="sxs-lookup"><span data-stu-id="e77b6-117">The page remains accessible, however, if you use Automation or UI paths that do not include the page name, for example, the **Print** command.</span></span> 
  
 <span data-ttu-id="e77b6-118">此单元格旨在用于文档页面; 例如：它不能用于标记贴页面，具有默认设置为**visUIVHidden** UIVisibility 单元格，并不应被更改。</span><span class="sxs-lookup"><span data-stu-id="e77b6-118">This cell is intended for use with document pages; it is not intended for use with markup overlay pages, which have the UIVisibility cell set to **visUIVHidden** by default and should not be changed.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e77b6-119">若要隐藏页上，从文档的**打印**命令，使其将背景页 （**Type**属性是**visTypeBackground** ） 不使用作为背景由任何页面 （当使用作为背景页打印页面的背景上的形状打印）。</span><span class="sxs-lookup"><span data-stu-id="e77b6-119">To hide a page from the document's **Print** command, make it a background page (**Type** property is **visTypeBackground** ) that is not used as a background by any page (shapes on background pages are printed when a page using it as a background is printed).</span></span> <span data-ttu-id="e77b6-120">文档的**打印**命令仅处理索引页和背景页不编制索引。</span><span class="sxs-lookup"><span data-stu-id="e77b6-120">The document's **Print** command only works with indexed pages, and background pages are not indexed.</span></span> 
  
<span data-ttu-id="e77b6-121">若要获取对 UIVisibility 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="e77b6-121">To get a reference to the UIVisibility cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e77b6-122">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e77b6-122">Cell name:</span></span>  <br/> |<span data-ttu-id="e77b6-123">UIVisibility</span><span class="sxs-lookup"><span data-stu-id="e77b6-123">UIVisibility</span></span>  <br/> |
   
<span data-ttu-id="e77b6-124">若要从某个程序按索引获取对 UIVisibility 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="e77b6-124">To get a reference to the UIVisibility cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e77b6-125">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e77b6-125">Section index:</span></span>  <br/> |<span data-ttu-id="e77b6-126">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e77b6-126">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="e77b6-127">行索引：</span><span class="sxs-lookup"><span data-stu-id="e77b6-127">Row index:</span></span>  <br/> |<span data-ttu-id="e77b6-128">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="e77b6-128">**visRowPage**</span></span> <br/> |
|<span data-ttu-id="e77b6-129">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e77b6-129">Cell index:</span></span>  <br/> |<span data-ttu-id="e77b6-130">**visPageUIVisibility**</span><span class="sxs-lookup"><span data-stu-id="e77b6-130">**visPageUIVisibility**</span></span> <br/> |
   

