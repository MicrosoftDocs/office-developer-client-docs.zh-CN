---
title: Menu 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm690
localization_priority: Normal
ms.assetid: 29af746c-b081-24cf-a30d-a56353ee849e
description: 定义形状或页的快捷菜单或动作标记菜单上显示的菜单项的名称。
ms.openlocfilehash: adb6915c34946472ada8c4ab4d02fa88bab6651a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436326"
---
# <a name="menu-cell-actions-section"></a><span data-ttu-id="7d488-103">Menu 单元格（“Actions”内容）</span><span class="sxs-lookup"><span data-stu-id="7d488-103">Menu Cell (Actions Section)</span></span>

<span data-ttu-id="7d488-104">定义形状或页的快捷菜单或动作标记菜单上显示的菜单项的名称。</span><span class="sxs-lookup"><span data-stu-id="7d488-104">Defines the name of a menu item that appears on a shortcut or action tag menu for a shape or page.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7d488-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="7d488-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="7d488-106">备注</span><span class="sxs-lookup"><span data-stu-id="7d488-106">Remarks</span></span>

<span data-ttu-id="7d488-p101">若要在此项之上将分隔符插入菜单，请使用 BeginGroup 单元格。要在菜单底部显示命令，请在命令名之前加百分号字符 (%) 前缀。</span><span class="sxs-lookup"><span data-stu-id="7d488-p101">To insert a separator into the menu above this item, use the BeginGroup cell. To display the command at the bottom of the menu, prefix the name with a percent character (%) .</span></span>
  
<span data-ttu-id="7d488-109">若要从另一个公式或使用 **CellsU** 属性从程序按名称获取对 Menu 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7d488-109">To get a reference to the Menu cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7d488-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7d488-110">Cell name:</span></span>  <br/> |<span data-ttu-id="7d488-111">操作。</span><span class="sxs-lookup"><span data-stu-id="7d488-111">Actions.</span></span> <span data-ttu-id="7d488-112">*name*  .Menuwhere Actions.</span><span class="sxs-lookup"><span data-stu-id="7d488-112">*name*  .Menuwhere Actions.</span></span>  <span data-ttu-id="7d488-113">*name*  是 Actions 行的名称</span><span class="sxs-lookup"><span data-stu-id="7d488-113">*name*  is the name of the Actions row</span></span>  <br/> |
   
<span data-ttu-id="7d488-114">若要从某个程序按索引获取对 Menu 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7d488-114">To get a reference to the Menu cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7d488-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7d488-115">Section index:</span></span>  <br/> |<span data-ttu-id="7d488-116">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="7d488-116">**visSectionAction**</span></span> <br/> |
|<span data-ttu-id="7d488-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="7d488-117">Row index:</span></span>  <br/> |<span data-ttu-id="7d488-118">**visRowAction**  +  *i* 其中 i = 0， 1， 2， ...</span><span class="sxs-lookup"><span data-stu-id="7d488-118">**visRowAction** +  *i*  where i = 0, 1, 2, ...</span></span>  <br/> |
|<span data-ttu-id="7d488-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7d488-119">Cell index:</span></span>  <br/> |<span data-ttu-id="7d488-120">**visActionMenu**</span><span class="sxs-lookup"><span data-stu-id="7d488-120">**visActionMenu**</span></span> <br/> |
   

