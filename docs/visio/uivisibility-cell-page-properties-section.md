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
ms.openlocfilehash: 51ccd34cb40c286fe6b61818aea5a6b9c0b6d1a4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437327"
---
# <a name="uivisibility-cell-page-properties-section"></a><span data-ttu-id="a4cdb-103">UIVisibility 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="a4cdb-103">UIVisibility Cell (Page Properties Section)</span></span>

<span data-ttu-id="a4cdb-104">确定用户界面 (UI) 中是否显示页名称。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-104">Determines whether the page name is exposed in the user interface (UI).</span></span>
  
|<span data-ttu-id="a4cdb-105">**值**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-105">**Value**</span></span>|<span data-ttu-id="a4cdb-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-106">**Description**</span></span>|<span data-ttu-id="a4cdb-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4cdb-108">0</span><span class="sxs-lookup"><span data-stu-id="a4cdb-108">0</span></span>  <br/> |<span data-ttu-id="a4cdb-109">在 UI 中显示页名称（默认值）。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-109">Display the page name in the UI (the default).</span></span>  <br/> |<span data-ttu-id="a4cdb-110">**visUIVNormal**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-110">**visUIVNormal**</span></span> <br/> |
|<span data-ttu-id="a4cdb-111">1</span><span class="sxs-lookup"><span data-stu-id="a4cdb-111">1</span></span>  <br/> |<span data-ttu-id="a4cdb-112">在 UI 中不显示页名称。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-112">Do not display the page name in the UI.</span></span>  <br/> |<span data-ttu-id="a4cdb-113">**visUIVHidden**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-113">**visUIVHidden**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a4cdb-114">备注</span><span class="sxs-lookup"><span data-stu-id="a4cdb-114">Remarks</span></span>

<span data-ttu-id="a4cdb-115">通过将 UIVisibility 单元格设置为 **visUIVHidden**，可避免 UI 中在出现含有页名称的字符串的任何位置显示该页。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-115">Setting the UIVisibility cell to **visUIVHidden** prevents the page from appearing anywhere in the UI where the string containing the page name appears.</span></span> <span data-ttu-id="a4cdb-116">例如，该页不会作为 **“绘图资源管理器”** 中的选项列出，也不会在页标签上列出。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-116">For example, the page would not be listed as an option in the **Drawing Explorer** or on the page tabs.</span></span> <span data-ttu-id="a4cdb-117">但是，如果您使用不包含页面名称的自动化或 UI 路径（例如 **，Print** 命令）来访问该页面。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-117">The page remains accessible, however, if you use Automation or UI paths that do not include the page name, for example, the **Print** command.</span></span> 
  
 <span data-ttu-id="a4cdb-118">此单元格设计用于文档页；而不是用于标记贴页，标记贴页的 UIVisibility 单元格默认设置为 **visUIVHidden**，并且不应改变。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-118">This cell is intended for use with document pages; it is not intended for use with markup overlay pages, which have the UIVisibility cell set to **visUIVHidden** by default and should not be changed.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a4cdb-119">若要从文档的 **"** 打印"命令中隐藏页面，请将其作为背景页 (**Type** 属性是 **visTypeBackground** ) ，当打印使用页面作为背景的页面时) 将打印背景页上的任何页面 (形状不用作背景。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-119">To hide a page from the document's **Print** command, make it a background page (**Type** property is **visTypeBackground** ) that is not used as a background by any page (shapes on background pages are printed when a page using it as a background is printed).</span></span> <span data-ttu-id="a4cdb-120">文档的 **"打印"** 命令仅适用于索引页，并且不为背景页编制索引。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-120">The document's **Print** command only works with indexed pages, and background pages are not indexed.</span></span> 
  
<span data-ttu-id="a4cdb-121">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 UIVisibility 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a4cdb-121">To get a reference to the UIVisibility cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a4cdb-122">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a4cdb-122">Cell name:</span></span>  <br/> |<span data-ttu-id="a4cdb-123">UIVisibility</span><span class="sxs-lookup"><span data-stu-id="a4cdb-123">UIVisibility</span></span>  <br/> |
   
<span data-ttu-id="a4cdb-124">若要从某个程序按索引获取对 UIVisibility 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="a4cdb-124">To get a reference to the UIVisibility cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a4cdb-125">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a4cdb-125">Section index:</span></span>  <br/> |<span data-ttu-id="a4cdb-126">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-126">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="a4cdb-127">行索引：</span><span class="sxs-lookup"><span data-stu-id="a4cdb-127">Row index:</span></span>  <br/> |<span data-ttu-id="a4cdb-128">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-128">**visRowPage**</span></span> <br/> |
|<span data-ttu-id="a4cdb-129">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a4cdb-129">Cell index:</span></span>  <br/> |<span data-ttu-id="a4cdb-130">**visPageUIVisibility**</span><span class="sxs-lookup"><span data-stu-id="a4cdb-130">**visPageUIVisibility**</span></span> <br/> |
   

