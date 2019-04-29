---
title: PageWidth 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251372
localization_priority: Normal
ms.assetid: b98c5bf3-10c8-7299-2836-3906d6a9135d
description: 确定以绘图单位表示的打印页面的宽度。
ms.openlocfilehash: 6d887cb4335d2725101db54ba2b1483ccf01cff4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434268"
---
# <a name="pagewidth-cell-page-properties-section"></a><span data-ttu-id="beee9-103">PageWidth 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="beee9-103">PageWidth Cell (Page Properties Section)</span></span>

<span data-ttu-id="beee9-104">确定以绘图单位表示的打印页面的宽度。</span><span class="sxs-lookup"><span data-stu-id="beee9-104">Determines the width of the printed page in drawing units.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="beee9-105">说明</span><span class="sxs-lookup"><span data-stu-id="beee9-105">Remarks</span></span>

<span data-ttu-id="beee9-106">您还可以在 "**页面设置**" 对话框 (在 "**设计**" 选项卡上, 单击 "**页面设置**" 箭头) 的 "**页面大小**" 选项卡上设置页面宽度, 或使用鼠标手动调整页面大小。</span><span class="sxs-lookup"><span data-stu-id="beee9-106">You can also set the page width on the **Page Size** tab of the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow) or by manually resizing the page with the mouse.</span></span> <span data-ttu-id="beee9-107">若要手动调整页面大小，请按住 Ctrl 键，同时拖动页面的边缘。</span><span class="sxs-lookup"><span data-stu-id="beee9-107">To do this, drag the edge of the page while holding down the CTRL key.</span></span> 
  
<span data-ttu-id="beee9-108">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PageWidth 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="beee9-108">To get a reference to the PageWidth cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="beee9-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="beee9-109">Cell name:</span></span>  <br/> |<span data-ttu-id="beee9-110">PageWidth</span><span class="sxs-lookup"><span data-stu-id="beee9-110">PageWidth</span></span>  <br/> |
   
<span data-ttu-id="beee9-111">若要从某个程序按索引获取对 PageWidth 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="beee9-111">To get a reference to the PageWidth cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="beee9-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="beee9-112">Section index:</span></span>  <br/> |<span data-ttu-id="beee9-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="beee9-113">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="beee9-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="beee9-114">Row index:</span></span>  <br/> |<span data-ttu-id="beee9-115">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="beee9-115">**visRowPage**</span></span> <br/> |
|<span data-ttu-id="beee9-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="beee9-116">Cell index:</span></span>  <br/> |<span data-ttu-id="beee9-117">**visPageWidth**</span><span class="sxs-lookup"><span data-stu-id="beee9-117">**visPageWidth**</span></span> <br/> |
   

