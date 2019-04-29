---
title: BeginGroup 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60022
localization_priority: Normal
ms.assetid: 1ae7f629-fb9f-1a11-1194-b381d6c9de5b
description: 指示是否在此动作之上的菜单中插入分隔符。
ms.openlocfilehash: 115dbfe051201dc3ec2b127ff129b077e1067865
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407835"
---
# <a name="begingroup-cell-actions-section"></a><span data-ttu-id="39813-103">BeginGroup 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="39813-103">BeginGroup Cell (Actions Section)</span></span>

<span data-ttu-id="39813-104">指示是否在此动作之上的菜单中插入分隔符。</span><span class="sxs-lookup"><span data-stu-id="39813-104">Indicates whether a separator is inserted into the menu above this action.</span></span> 
  
|<span data-ttu-id="39813-105">**值**</span><span class="sxs-lookup"><span data-stu-id="39813-105">**Value**</span></span>|<span data-ttu-id="39813-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="39813-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="39813-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="39813-107">TRUE</span></span>  <br/> |<span data-ttu-id="39813-108">在此动作之上的菜单中插入分隔符。</span><span class="sxs-lookup"><span data-stu-id="39813-108">A separator is inserted into the menu above this action.</span></span>  <br/> |
|<span data-ttu-id="39813-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="39813-109">FALSE</span></span>  <br/> |<span data-ttu-id="39813-110">未在此动作之上的菜单中插入分隔符（默认值）。</span><span class="sxs-lookup"><span data-stu-id="39813-110">A separator is not inserted into the menu above this action (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="39813-111">说明</span><span class="sxs-lookup"><span data-stu-id="39813-111">Remarks</span></span>

<span data-ttu-id="39813-112">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 BeginGroup 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="39813-112">To get a reference to the BeginGroup cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="39813-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="39813-113">Cell name:</span></span>  <br/> |<span data-ttu-id="39813-114">操作.</span><span class="sxs-lookup"><span data-stu-id="39813-114">Actions.</span></span> <span data-ttu-id="39813-115">*名称*。BeginGroup 其中的操作。</span><span class="sxs-lookup"><span data-stu-id="39813-115">*name*.BeginGroup where Actions.</span></span> <span data-ttu-id="39813-116">*name* 是 Actions 行的名称</span><span class="sxs-lookup"><span data-stu-id="39813-116">*name* is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="39813-117">若要从某个程序按索引获取对 BeginGroup 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="39813-117">To get a reference to the BeginGroup cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="39813-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="39813-118">Section index:</span></span>  <br/> |<span data-ttu-id="39813-119">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="39813-119">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="39813-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="39813-120">Row index:</span></span>  <br/> |<span data-ttu-id="39813-121">**visRowAction** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="39813-121">**visRowAction** +  *i*           where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="39813-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="39813-122">Cell index:</span></span>  <br/> |<span data-ttu-id="39813-123">**visActionBeginGroup**</span><span class="sxs-lookup"><span data-stu-id="39813-123">**visActionBeginGroup**</span></span> <br/> |
   

