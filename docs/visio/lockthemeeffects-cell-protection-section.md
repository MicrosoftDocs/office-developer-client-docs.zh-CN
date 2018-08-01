---
title: LockThemeEffects 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm70002
localization_priority: Normal
ms.assetid: 84179718-d7a6-d503-08f2-213571bf108f
ms.openlocfilehash: 41c9e9c021c5ad954c16599f9e376063655ffa07
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780648"
---
# <a name="lockthemeeffects-cell-protection-section"></a><span data-ttu-id="f516e-102">LockThemeEffects 单元格（“Protection”部分）</span><span class="sxs-lookup"><span data-stu-id="f516e-102">LockThemeEffects Cell (Protection Section)</span></span>

<span data-ttu-id="f516e-103">防止对形状应用主题效果。</span><span class="sxs-lookup"><span data-stu-id="f516e-103">Prevents application of theme effects to the shape.</span></span> 
  
<span data-ttu-id="f516e-104">与**保护**对话框中的**阻止应用主题效果**复选框设置相对应。</span><span class="sxs-lookup"><span data-stu-id="f516e-104">Corresponds to the **From theme effects** check box setting in the **Protection** dialog box.</span></span> 
  
<span data-ttu-id="f516e-105">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称引用 LockThemeColors 单元格，请使用：

</span><span class="sxs-lookup"><span data-stu-id="f516e-105">To refer ti the LockThemeColors cell by name from another formula, or from a program, using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f516e-106">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f516e-106">Cell name:</span></span>  <br/> |<span data-ttu-id="f516e-107">LockThemeEffects</span><span class="sxs-lookup"><span data-stu-id="f516e-107">LockThemeEffects</span></span>  <br/> |
   
<span data-ttu-id="f516e-108">若要从某个程序按索引引用 LockThemeEffects 单元格，请使用带下列参数的 **CellsSRC** 属性：

</span><span class="sxs-lookup"><span data-stu-id="f516e-108">To refer to the LockThemeEffects cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f516e-109">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f516e-109">Section index:</span></span>  <br/> |<span data-ttu-id="f516e-110">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f516e-110">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="f516e-111">行索引：</span><span class="sxs-lookup"><span data-stu-id="f516e-111">Row index:</span></span>  <br/> |<span data-ttu-id="f516e-112">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="f516e-112">**visRowLock**</span></span> <br/> |
|<span data-ttu-id="f516e-113">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f516e-113">Cell index:</span></span>  <br/> |<span data-ttu-id="f516e-114">**visLockThemeEffects**</span><span class="sxs-lookup"><span data-stu-id="f516e-114">**visLockThemeEffects**</span></span> <br/> |
   

