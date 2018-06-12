---
title: NoCtlHandles 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251319
localization_priority: Normal
ms.assetid: 4345b3e5-f522-e300-307c-4f8992a3ddce
description: 切换选中形状的控制手柄的显示状态 - 显示或不显示。
ms.openlocfilehash: 897e4cd97eeab8797f2652285ba395603c41a8e7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780784"
---
# <a name="noctlhandles-cell-miscellaneous-section"></a><span data-ttu-id="f215f-103">NoCtlHandles 单元格（“Miscellaneous”内容）</span><span class="sxs-lookup"><span data-stu-id="f215f-103">NoCtlHandles Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="f215f-104">切换选中形状的控制手柄的显示状态 - 显示或不显示。</span><span class="sxs-lookup"><span data-stu-id="f215f-104">Switches the display of control handles on and off for the selected shape.</span></span>
  
|<span data-ttu-id="f215f-105">**值**</span><span class="sxs-lookup"><span data-stu-id="f215f-105">**Value**</span></span>|<span data-ttu-id="f215f-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="f215f-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="f215f-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="f215f-107">TRUE</span></span>  <br/> | <span data-ttu-id="f215f-108">选中形状后不显示控制手柄。</span><span class="sxs-lookup"><span data-stu-id="f215f-108">Control handles are not displayed when a shape is selected.</span></span>  <br/> |
| <span data-ttu-id="f215f-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="f215f-109">FALSE</span></span>  <br/> | <span data-ttu-id="f215f-110">选中形状后显示控制手柄。</span><span class="sxs-lookup"><span data-stu-id="f215f-110">Control handles are displayed when a shape is selected.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f215f-111">注解</span><span class="sxs-lookup"><span data-stu-id="f215f-111">Remarks</span></span>

<span data-ttu-id="f215f-112">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 NoCtlHandles 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f215f-112">To get a reference to the NoCtlHandles cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f215f-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f215f-113">Cell name:</span></span>  <br/> | <span data-ttu-id="f215f-114">NoCtlHandles</span><span class="sxs-lookup"><span data-stu-id="f215f-114">NoCtlHandles</span></span>  <br/> |
   
<span data-ttu-id="f215f-115">若要从某个程序按索引获取对 NoCtlHandles 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="f215f-115">To get a reference to the NoCtlHandles cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f215f-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f215f-116">Section index:</span></span>  <br/> |<span data-ttu-id="f215f-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f215f-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="f215f-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="f215f-118">Row index:</span></span>  <br/> |<span data-ttu-id="f215f-119">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="f215f-119">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="f215f-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f215f-120">Cell index:</span></span>  <br/> |<span data-ttu-id="f215f-121">**visNoCtlHandles**</span><span class="sxs-lookup"><span data-stu-id="f215f-121">**visNoCtlHandles**</span></span> <br/> |
   

