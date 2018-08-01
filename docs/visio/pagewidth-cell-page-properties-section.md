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
ms.openlocfilehash: e03696c8f1c921c930d3563e9c73ef4ae613a7c1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780848"
---
# <a name="pagewidth-cell-page-properties-section"></a><span data-ttu-id="4af6a-103">PageWidth 单元格（“Page Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="4af6a-103">PageWidth Cell (Page Properties Section)</span></span>

<span data-ttu-id="4af6a-104">确定以绘图单位表示的打印页面的宽度。</span><span class="sxs-lookup"><span data-stu-id="4af6a-104">Determines the width of the printed page in drawing units.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4af6a-105">注解</span><span class="sxs-lookup"><span data-stu-id="4af6a-105">Remarks</span></span>

<span data-ttu-id="4af6a-106">您还可以在**页面设置**对话框的**页面大小**选项卡上设置页宽 （在**设计**选项卡上，单击**页面设置**箭头） 或手动调整鼠标的页面。</span><span class="sxs-lookup"><span data-stu-id="4af6a-106">You can also set the page width on the **Page Size** tab of the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow) or by manually resizing the page with the mouse.</span></span> <span data-ttu-id="4af6a-107">若要执行此操作，请在按住 CTRL 键的同时拖动页上的边缘。</span><span class="sxs-lookup"><span data-stu-id="4af6a-107">To do this, drag the edge of the page while holding down the CTRL key.</span></span> 
  
<span data-ttu-id="4af6a-108">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PageWidth 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4af6a-108">To get a reference to the PageWidth cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4af6a-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4af6a-109">Cell name:</span></span>  <br/> |<span data-ttu-id="4af6a-110">PageWidth</span><span class="sxs-lookup"><span data-stu-id="4af6a-110">PageWidth</span></span>  <br/> |
   
<span data-ttu-id="4af6a-111">若要从某个程序按索引获取对 PageWidth 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4af6a-111">To get a reference to the PageWidth cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4af6a-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4af6a-112">Section index:</span></span>  <br/> |<span data-ttu-id="4af6a-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4af6a-113">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="4af6a-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="4af6a-114">Row index:</span></span>  <br/> |<span data-ttu-id="4af6a-115">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="4af6a-115">**visRowPage**</span></span> <br/> |
|<span data-ttu-id="4af6a-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4af6a-116">Cell index:</span></span>  <br/> |<span data-ttu-id="4af6a-117">**visPageWidth**</span><span class="sxs-lookup"><span data-stu-id="4af6a-117">**visPageWidth**</span></span> <br/> |
   

