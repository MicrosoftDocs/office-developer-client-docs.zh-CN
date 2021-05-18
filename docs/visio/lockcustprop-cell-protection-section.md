---
title: LockCustProp 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60055
localization_priority: Normal
ms.assetid: d1c23f1d-485d-a897-594d-15d6e8d0fb3c
description: 确定用户是否可以使用“定义形状数据”对话框或“形状数据”窗口的快捷菜单在用户界面 (UI) 中添加、删除或修改形状数据。
ms.openlocfilehash: 001123f3bd08d35f6f8e4874e20f2ee073835494
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422521"
---
# <a name="lockcustprop-cell-protection-section"></a><span data-ttu-id="d4ec5-103">LockCustProp 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="d4ec5-103">LockCustProp Cell (Protection Section)</span></span>

<span data-ttu-id="d4ec5-104">确定用户是否可以使用 **“定义形状数据”** 对话框或 **“形状数据”** 窗口的快捷菜单在用户界面 (UI) 中添加、删除或修改形状数据。</span><span class="sxs-lookup"><span data-stu-id="d4ec5-104">Determines whether the user can add, delete, or modify shape data in the user interface (UI) by using the **Define Shape Data** dialog box or the shortcut menu for the **Shape Data** window.</span></span> 
  
|<span data-ttu-id="d4ec5-105">**值**</span><span class="sxs-lookup"><span data-stu-id="d4ec5-105">**Value**</span></span>|<span data-ttu-id="d4ec5-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="d4ec5-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ec5-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="d4ec5-107">TRUE</span></span>  <br/> |<span data-ttu-id="d4ec5-108">**“形状数据”** 窗口中的快捷菜单上的 **“定义形状数据”** 命令被禁用。</span><span class="sxs-lookup"><span data-stu-id="d4ec5-108">The **Define Shape Data** command on the shortcut menu in the **Shape Data** window is disabled.</span></span>  <br/> |
|<span data-ttu-id="d4ec5-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="d4ec5-109">FALSE</span></span>  <br/> |<span data-ttu-id="d4ec5-110">**“形状数据”** 窗口中的快捷菜单上的 **“定义形状数据”** 命令被启用（默认值）。</span><span class="sxs-lookup"><span data-stu-id="d4ec5-110">The **Define Shape Data** command on the shortcut menu in the **Shape Data** window is enabled (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d4ec5-111">备注</span><span class="sxs-lookup"><span data-stu-id="d4ec5-111">Remarks</span></span>

<span data-ttu-id="d4ec5-112">值为 TRUE 则表示不禁止用户更改形状数据项的值，或者不禁止用户在 ShapeSheet 窗口中更改“Shape Data”内容。</span><span class="sxs-lookup"><span data-stu-id="d4ec5-112">A value of TRUE does not prevent a user from changing the value of a shape data item or changing the Shape Data section in the ShapeSheet window.</span></span> 
  
<span data-ttu-id="d4ec5-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LockCustProp 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d4ec5-113">To get a reference to the LockCustProp cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d4ec5-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d4ec5-114">Cell name:</span></span>  <br/> |<span data-ttu-id="d4ec5-115">LockCustProp</span><span class="sxs-lookup"><span data-stu-id="d4ec5-115">LockCustProp</span></span>  <br/> |
   
<span data-ttu-id="d4ec5-116">若要从某个程序按索引获取对 LockCustProp 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d4ec5-116">To get a reference to the LockCustProp cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d4ec5-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d4ec5-117">Section index:</span></span>  <br/> |<span data-ttu-id="d4ec5-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="d4ec5-118">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="d4ec5-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="d4ec5-119">Row index:</span></span>  <br/> |<span data-ttu-id="d4ec5-120">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="d4ec5-120">**visRowLock**</span></span> <br/> |
|<span data-ttu-id="d4ec5-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d4ec5-121">Cell index:</span></span>  <br/> |<span data-ttu-id="d4ec5-122">**visLockCustProp**</span><span class="sxs-lookup"><span data-stu-id="d4ec5-122">**visLockCustProp**</span></span> <br/> |
   

