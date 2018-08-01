---
title: Frame 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm405
localization_priority: Normal
ms.assetid: f71d8737-92ef-1124-ba4a-b7e17305bd0a
description: 代表当应用程序作为活动文档在某一容器应用程序中打开时的目标框架名。默认值为空字符串。
ms.openlocfilehash: b94e5efd4a3fdf53e01f7518252852214a72c766
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780322"
---
# <a name="frame-cell-hyperlinks-section"></a><span data-ttu-id="3d7a4-104">Frame 单元格（“Hyperlinks”部分）</span><span class="sxs-lookup"><span data-stu-id="3d7a4-104">Frame Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="3d7a4-p102">代表当应用程序作为活动文档在某一容器应用程序中打开时的目标框架名。默认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="3d7a4-p102">Represents the name of a frame to target when the application is open as an Active document in a container application. The default is an empty string.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3d7a4-107">注释</span><span class="sxs-lookup"><span data-stu-id="3d7a4-107">Remarks</span></span>

<span data-ttu-id="3d7a4-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Frame 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="3d7a4-108">To get a reference to the Frame cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3d7a4-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3d7a4-109">Cell name:</span></span>  <br/> | <span data-ttu-id="3d7a4-110">超链接。</span><span class="sxs-lookup"><span data-stu-id="3d7a4-110">Hyperlink.</span></span>  <span data-ttu-id="3d7a4-111">*名称*。框位置的超链接。</span><span class="sxs-lookup"><span data-stu-id="3d7a4-111">*name*  .Frame            where Hyperlink.</span></span>  <span data-ttu-id="3d7a4-112">*name*是行名称</span><span class="sxs-lookup"><span data-stu-id="3d7a4-112">*name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="3d7a4-113">要从某个程序按索引获取对 Frame 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="3d7a4-113">To get a reference to the Frame cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3d7a4-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3d7a4-114">Section index:</span></span>  <br/> |<span data-ttu-id="3d7a4-115">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="3d7a4-115">**visSectionHyperlink**</span></span> <br/> |
| <span data-ttu-id="3d7a4-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="3d7a4-116">Row index:</span></span>  <br/> |<span data-ttu-id="3d7a4-117">**visRow1stHyperlink** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="3d7a4-117">**visRow1stHyperlink** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="3d7a4-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3d7a4-118">Cell index:</span></span>  <br/> |<span data-ttu-id="3d7a4-119">**visHLinkFrame**</span><span class="sxs-lookup"><span data-stu-id="3d7a4-119">**visHLinkFrame**</span></span> <br/> |
   

