---
title: ButtonFace 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60025
localization_priority: Normal
ms.assetid: cf15b879-a47e-a5a5-bfdd-1d7ea423742f
description: 标识在快捷菜单或动作标记菜单上的项旁边显示的图标。
ms.openlocfilehash: 7ee9c4e7e857acb34ce75429aa0aaf679320b0e8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337546"
---
# <a name="buttonface-cell-actions-section"></a><span data-ttu-id="386c2-103">ButtonFace 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="386c2-103">ButtonFace Cell (Actions Section)</span></span>

<span data-ttu-id="386c2-104">标识在快捷菜单或动作标记菜单上的项旁边显示的图标。</span><span class="sxs-lookup"><span data-stu-id="386c2-104">Identifies the icon that appears next to an item on a shortcut or action tag menu.</span></span>
  
> [!NOTE]
> <span data-ttu-id="386c2-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="386c2-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="386c2-106">注解</span><span class="sxs-lookup"><span data-stu-id="386c2-106">Remarks</span></span>

<span data-ttu-id="386c2-p101">ButtonFace 单元格中包含的字符串表示 Microsoft Office 按钮外表图像的 ID。值为零 (0) 或空白表示不显示图标。</span><span class="sxs-lookup"><span data-stu-id="386c2-p101">The string contained in the ButtonFace cell represents the ID of a Microsoft Office button face image. A value of zero (0) or blank means no icon appears.</span></span> 
  
<span data-ttu-id="386c2-109">ButtonFace 单元格中可以使用的 ID 与用于 **CommandBarButton** 对象的 **FaceID** 属性的 ID 相同。</span><span class="sxs-lookup"><span data-stu-id="386c2-109">The IDs that can be used in the ButtonFace cell are the same as the IDs used with the **FaceID** property of a **CommandBarButton** object.</span></span> <span data-ttu-id="386c2-110">有关这些 id 的更多详细信息, 请在 MSDN 上搜索 "使用命令栏按钮图像"。</span><span class="sxs-lookup"><span data-stu-id="386c2-110">For more details about these IDs, search for "working with command bar button images" on MSDN.</span></span> 
  
<span data-ttu-id="386c2-111">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称来获取对 ButtonFace 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="386c2-111">To get a reference to the ButtonFace cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="386c2-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="386c2-112">Cell name:</span></span>  <br/> |<span data-ttu-id="386c2-113">**操作**。</span><span class="sxs-lookup"><span data-stu-id="386c2-113">**Actions**.</span></span>  <span data-ttu-id="386c2-114">*名称*。</span><span class="sxs-lookup"><span data-stu-id="386c2-114">*name*  .</span></span> <span data-ttu-id="386c2-115">**ButtonFace**其中的**操作**。</span><span class="sxs-lookup"><span data-stu-id="386c2-115">**ButtonFace**         where **Actions**.</span></span>  <span data-ttu-id="386c2-116">*name*是操作行的名称</span><span class="sxs-lookup"><span data-stu-id="386c2-116">*name*  is the name of the actions row</span></span>  <br/> |
   
<span data-ttu-id="386c2-117">要从某个程序按索引获取有关 ButtonFace 单元格的参考内容，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="386c2-117">To get a reference to the ButtonFace cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="386c2-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="386c2-118">Section index:</span></span>  <br/> |<span data-ttu-id="386c2-119">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="386c2-119">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="386c2-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="386c2-120">Row index:</span></span>  <br/> |<span data-ttu-id="386c2-121">**visRowAction** +  *i* = \*\*\*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="386c2-121">**visRowAction** +  *i*           where **i** = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="386c2-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="386c2-122">Cell index:</span></span>  <br/> |<span data-ttu-id="386c2-123">**visActionButtonFace**</span><span class="sxs-lookup"><span data-stu-id="386c2-123">**visActionButtonFace**</span></span> <br/> |
   

