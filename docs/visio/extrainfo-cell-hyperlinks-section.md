---
title: ExtraInfo 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm360
localization_priority: Normal
ms.assetid: 55834445-8619-f79a-aea0-0f6a1780e016
description: 表示传递解析 URL 所需信息的字符串，如图像映射的坐标。 例如, 在 ExtraInfo 单元格中, x = 41&amp;y = 7specifies 图像映射的坐标。
ms.openlocfilehash: df2886ef7911b484cc60e8a476bfa53369fbf646
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357818"
---
# <a name="extrainfo-cell-hyperlinks-section"></a><span data-ttu-id="ec971-104">ExtraInfo 单元格（“Hyperlinks”内容）</span><span class="sxs-lookup"><span data-stu-id="ec971-104">ExtraInfo Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="ec971-105">表示传递解析 URL 所需信息的字符串，如图像映射的坐标。</span><span class="sxs-lookup"><span data-stu-id="ec971-105">Represents a string that passes information to be used in resolving a URL, such as the coordinates of an image map.</span></span> <span data-ttu-id="ec971-106">例如, 在 ExtraInfo 单元格中, "x = 41&amp;y = 7" 指定图像映射的坐标。</span><span class="sxs-lookup"><span data-stu-id="ec971-106">For example, in the ExtraInfo cell, "x=41&amp;y=7" specifies the coordinates of an image map.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ec971-107">注解</span><span class="sxs-lookup"><span data-stu-id="ec971-107">Remarks</span></span>

<span data-ttu-id="ec971-108">只在事件发生后（而非输入公式后）才对事件单元格求值。</span><span class="sxs-lookup"><span data-stu-id="ec971-108">Event cells are evaluated only when the event occurs, not upon formula entry.</span></span>
  
<span data-ttu-id="ec971-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ExtraInfo 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ec971-109">To get a reference to the ExtraInfo cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ec971-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ec971-110">Cell name:</span></span>  <br/> | <span data-ttu-id="ec971-111">超链接。</span><span class="sxs-lookup"><span data-stu-id="ec971-111">Hyperlink.</span></span>  <span data-ttu-id="ec971-112">*名称*。ExtraInfo 其中的超链接。</span><span class="sxs-lookup"><span data-stu-id="ec971-112">*name*  .ExtraInfo            where Hyperlink.</span></span>  <span data-ttu-id="ec971-113">*名称*是行名称</span><span class="sxs-lookup"><span data-stu-id="ec971-113">*name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="ec971-114">要从某个程序按索引获取对 ExtraInfo 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ec971-114">To get a reference to the ExtraInfo cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ec971-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ec971-115">Section index:</span></span>  <br/> |<span data-ttu-id="ec971-116">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="ec971-116">**visSectionHyperlink**</span></span> <br/> |
| <span data-ttu-id="ec971-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="ec971-117">Row index:</span></span>  <br/> |<span data-ttu-id="ec971-118">**visRow1stHyperlink** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="ec971-118">**visRow1stHyperlink** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="ec971-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ec971-119">Cell index:</span></span>  <br/> |<span data-ttu-id="ec971-120">**visHLinkExtraInfo**</span><span class="sxs-lookup"><span data-stu-id="ec971-120">**visHLinkExtraInfo**</span></span> <br/> |
   

