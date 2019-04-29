---
title: LockThemeColors 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm70001
localization_priority: Normal
ms.assetid: 22cedeb3-58b5-3932-9252-5c9dd3e163e3
ms.openlocfilehash: 81091ea33be2158435d240ba14f3c97e8f3fcc39
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436844"
---
# <a name="lockthemecolors-cell-protection-section"></a><span data-ttu-id="953ca-102">LockThemeColors 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="953ca-102">LockThemeColors Cell (Protection Section)</span></span>

<span data-ttu-id="953ca-103">阻止将主题颜色应用到形状。</span><span class="sxs-lookup"><span data-stu-id="953ca-103">Prevents application of theme colors to the shape.</span></span> 
  
<span data-ttu-id="953ca-104">LockThemeColors 单元格的值与 **“保护”** 对话框中的 **“阻止应用主题颜色”** 复选框设置相对应。</span><span class="sxs-lookup"><span data-stu-id="953ca-104">The value of the LockThemeColors cell corresponds to the **From theme colors** check box setting in the **Protection** dialog box.</span></span> 
  
<span data-ttu-id="953ca-105">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称引用 LockThemeColors 单元格，请使用：

</span><span class="sxs-lookup"><span data-stu-id="953ca-105">To refer to the LockThemeColors cell by name from another formula, or from a program, using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="953ca-106">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="953ca-106">Cell name:</span></span>  <br/> |<span data-ttu-id="953ca-107">LockThemeColors</span><span class="sxs-lookup"><span data-stu-id="953ca-107">LockThemeColors</span></span>  <br/> |
   
<span data-ttu-id="953ca-108">若要从某个程序按索引引用 LockThemeColors 单元格，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="953ca-108">To refer to the LockThemeColors cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="953ca-109">内容索引：</span><span class="sxs-lookup"><span data-stu-id="953ca-109">Section index:</span></span>  <br/> |<span data-ttu-id="953ca-110">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="953ca-110">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="953ca-111">行索引：</span><span class="sxs-lookup"><span data-stu-id="953ca-111">Row index:</span></span>  <br/> |<span data-ttu-id="953ca-112">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="953ca-112">**visRowLock**</span></span> <br/> |
|<span data-ttu-id="953ca-113">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="953ca-113">Cell index:</span></span>  <br/> |<span data-ttu-id="953ca-114">**visLockThemeColors**</span><span class="sxs-lookup"><span data-stu-id="953ca-114">**visLockThemeColors**</span></span> <br/> |
   

