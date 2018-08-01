---
title: Action 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm5
localization_priority: Normal
ms.assetid: 435e49ee-0b51-8ce3-0589-3f0717026f4a
description: 包含当用户选择快捷菜单或动作标记菜单上的命令时要执行的公式。
ms.openlocfilehash: 123b05f9a08c4ffa656e08a51f019f888cf83ed4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779619"
---
# <a name="action-cell-actions-section"></a><span data-ttu-id="4c8c0-103">Action 单元格（“Actions”部分）</span><span class="sxs-lookup"><span data-stu-id="4c8c0-103">Action Cell (Actions Section)</span></span>

<span data-ttu-id="4c8c0-104">包含当用户选择快捷菜单或动作标记菜单上的命令时要执行的公式。</span><span class="sxs-lookup"><span data-stu-id="4c8c0-104">Contains the formula to be executed when a user chooses a command on a shortcut or action tag menu.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c8c0-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="4c8c0-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="4c8c0-106">注释</span><span class="sxs-lookup"><span data-stu-id="4c8c0-106">Remarks</span></span>

<span data-ttu-id="4c8c0-107">只有动作发生（而不是输入该公式）后才对 Action 单元格求值。</span><span class="sxs-lookup"><span data-stu-id="4c8c0-107">An Action cell is evaluated only when the action occurs, not when the formula is entered.</span></span>
  
<span data-ttu-id="4c8c0-108">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Action 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4c8c0-108">To get a reference to the the Action cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4c8c0-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4c8c0-109">Cell name:</span></span>  <br/> | <span data-ttu-id="4c8c0-110">操作。</span><span class="sxs-lookup"><span data-stu-id="4c8c0-110">Actions.</span></span>  <span data-ttu-id="4c8c0-111">*名称*。操作其中操作。</span><span class="sxs-lookup"><span data-stu-id="4c8c0-111">*name*  .Action           where Actions.</span></span> <span data-ttu-id="4c8c0-112">*name*是 actions 行的名称</span><span class="sxs-lookup"><span data-stu-id="4c8c0-112">*name*  is the name of the actions row</span></span>  <br/> |
   
<span data-ttu-id="4c8c0-113">要从某个程序按索引获取对 Action 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4c8c0-113">To get a reference to thethe Action cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4c8c0-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4c8c0-114">Section index:</span></span>  <br/> |<span data-ttu-id="4c8c0-115">**visSectionAction**</span><span class="sxs-lookup"><span data-stu-id="4c8c0-115">**visSectionAction**</span></span> <br/> |
| <span data-ttu-id="4c8c0-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="4c8c0-116">Row index:</span></span>  <br/> |<span data-ttu-id="4c8c0-117">**visRowAction** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="4c8c0-117">**visRowAction** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="4c8c0-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4c8c0-118">Cell index:</span></span>  <br/> |<span data-ttu-id="4c8c0-119">**visActionAction**</span><span class="sxs-lookup"><span data-stu-id="4c8c0-119">**visActionAction**</span></span> <br/> |
   

