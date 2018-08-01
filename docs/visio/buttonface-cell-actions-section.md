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
ms.openlocfilehash: 29ff71bc04e94f97f1526b28bd52c2846327eff1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779806"
---
# <a name="buttonface-cell-actions-section"></a><span data-ttu-id="4c65e-103">ButtonFace 单元格（“Actions”部分）</span><span class="sxs-lookup"><span data-stu-id="4c65e-103">ButtonFace Cell (Actions Section)</span></span>

<span data-ttu-id="4c65e-104">标识在快捷菜单或动作标记菜单上的项旁边显示的图标。</span><span class="sxs-lookup"><span data-stu-id="4c65e-104">Identifies the icon that appears next to an item on a shortcut or action tag menu.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c65e-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="4c65e-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="4c65e-106">注解</span><span class="sxs-lookup"><span data-stu-id="4c65e-106">Remarks</span></span>

<span data-ttu-id="4c65e-p101">ButtonFace 单元格中包含的字符串表示 Microsoft Office 按钮外表图像的 ID。值为零 (0) 或空白表示不显示图标。</span><span class="sxs-lookup"><span data-stu-id="4c65e-p101">The string contained in the ButtonFace cell represents the ID of a Microsoft Office button face image. A value of zero (0) or blank means no icon appears.</span></span> 
  
<span data-ttu-id="4c65e-109">可在 ButtonFace 单元格的 Id 是与**CommandBarButton**对象的**FaceID**属性一起使用的 Id 相同。</span><span class="sxs-lookup"><span data-stu-id="4c65e-109">The IDs that can be used in the ButtonFace cell are the same as the IDs used with the **FaceID** property of a **CommandBarButton** object.</span></span> <span data-ttu-id="4c65e-110">关于这些 Id 的详细信息，请在 MSDN 上中搜索"命令栏按钮图像处理"。</span><span class="sxs-lookup"><span data-stu-id="4c65e-110">For more details about these IDs, search for "working with command bar button images" on MSDN.</span></span> 
  
<span data-ttu-id="4c65e-111">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称来获取对 ButtonFace 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4c65e-111">To get a reference to the ButtonFace cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4c65e-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4c65e-112">Cell name:</span></span>  <br/> |<span data-ttu-id="4c65e-113">**操作**。</span><span class="sxs-lookup"><span data-stu-id="4c65e-113">**Actions**.</span></span>  <span data-ttu-id="4c65e-114">*名称*。</span><span class="sxs-lookup"><span data-stu-id="4c65e-114">*name*  .</span></span> <span data-ttu-id="4c65e-115">**ButtonFace**其中**操作**。</span><span class="sxs-lookup"><span data-stu-id="4c65e-115">**ButtonFace**         where **Actions**.</span></span>  <span data-ttu-id="4c65e-116">*name*是 actions 行的名称</span><span class="sxs-lookup"><span data-stu-id="4c65e-116">*name*  is the name of the actions row</span></span>  <br/> |
   
<span data-ttu-id="4c65e-117">要从某个程序按索引获取有关 ButtonFace 单元格的参考内容，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4c65e-117">To get a reference to the ButtonFace cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4c65e-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4c65e-118">Section index:</span></span>  <br/> |<span data-ttu-id="4c65e-119">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="4c65e-119">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="4c65e-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="4c65e-120">Row index:</span></span>  <br/> |<span data-ttu-id="4c65e-121">**visRowAction** +  *i*其中**i** = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="4c65e-121">**visRowAction** +  *i*           where **i** = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="4c65e-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4c65e-122">Cell index:</span></span>  <br/> |<span data-ttu-id="4c65e-123">**visActionButtonFace**</span><span class="sxs-lookup"><span data-stu-id="4c65e-123">**visActionButtonFace**</span></span> <br/> |
   

