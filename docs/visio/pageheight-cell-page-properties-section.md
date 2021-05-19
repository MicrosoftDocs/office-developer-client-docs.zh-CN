---
title: PageHeight 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm760
localization_priority: Normal
ms.assetid: 0184814c-2d67-6ad4-e336-5694612e518d
description: 包含以绘图单位表示的打印页面的高度。
ms.openlocfilehash: ac24bee517f29da333a445f276447c1aa682f01c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427078"
---
# <a name="pageheight-cell-page-properties-section"></a><span data-ttu-id="37e11-103">PageHeight 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="37e11-103">PageHeight Cell (Page Properties Section)</span></span>

<span data-ttu-id="37e11-104">包含以绘图单位表示的打印页面的高度。</span><span class="sxs-lookup"><span data-stu-id="37e11-104">Contains the height of the printed page in drawing units.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="37e11-105">备注</span><span class="sxs-lookup"><span data-stu-id="37e11-105">Remarks</span></span>

<span data-ttu-id="37e11-106">还可以在 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）的 **“页面尺寸”** 选项卡上设置页面高度，或使用鼠标手动调整页面大小。</span><span class="sxs-lookup"><span data-stu-id="37e11-106">You can also set the page height on the **Page Size** tab of the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow), or by manually resizing the page with the mouse.</span></span> 
  
<span data-ttu-id="37e11-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PageHeight 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="37e11-107">To get a reference to the PageHeight cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="37e11-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="37e11-108">Cell name:</span></span>  <br/> |<span data-ttu-id="37e11-109">PageHeight</span><span class="sxs-lookup"><span data-stu-id="37e11-109">PageHeight</span></span>  <br/> |
   
<span data-ttu-id="37e11-110">若要从某个程序按索引获取对 PageHeight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="37e11-110">To get a reference to the PageHeight cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="37e11-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="37e11-111">Section index:</span></span>  <br/> |<span data-ttu-id="37e11-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="37e11-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="37e11-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="37e11-113">Row index:</span></span>  <br/> |<span data-ttu-id="37e11-114">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="37e11-114">**visRowPage**</span></span> <br/> |
|<span data-ttu-id="37e11-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="37e11-115">Cell index:</span></span>  <br/> |<span data-ttu-id="37e11-116">**visPageHeight**</span><span class="sxs-lookup"><span data-stu-id="37e11-116">**visPageHeight**</span></span> <br/> |
   

