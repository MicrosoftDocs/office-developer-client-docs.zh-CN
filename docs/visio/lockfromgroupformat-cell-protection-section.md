---
title: LockFromGroupFormat 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: abd175af-ad4e-b84a-2687-2c9358653499
ms.openlocfilehash: 3daeb4704a33ba836cf82c9ab3517c6ca6be8db7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426056"
---
# <a name="lockfromgroupformat-cell-protection-section"></a><span data-ttu-id="56269-102">LockFromGroupFormat 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="56269-102">LockFromGroupFormat Cell (Protection Section)</span></span>

<span data-ttu-id="56269-103">阻止将组形状的格式更改传播到其子形状, 同时仍允许用户直接设置选定子形状的格式。</span><span class="sxs-lookup"><span data-stu-id="56269-103">Blocks format changes to a group shape from being propagated to its sub-shapes, while still allowing users to format selected sub-shapes directly.</span></span> 
  
<span data-ttu-id="56269-104">LockFromGroupFormat 单元格的值与 **“保护”** 对话框中的 **“阻止应用组格式”** 复选框设置相对应。</span><span class="sxs-lookup"><span data-stu-id="56269-104">The value of the LockFromGroupFormat cell corresponds to the **From group formatting** check box setting in the **Protection** dialog box.</span></span> 
  
<span data-ttu-id="56269-105">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称引用 LockFromGroupFormat 单元格，请使用：

</span><span class="sxs-lookup"><span data-stu-id="56269-105">To refer to the LockFromGroupFormat cell by name from another formula, or from a program, using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="56269-106">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="56269-106">Cell name:</span></span>  <br/> |<span data-ttu-id="56269-107">LockFromGroupFormat</span><span class="sxs-lookup"><span data-stu-id="56269-107">LockFromGroupFormat</span></span>  <br/> |
   
<span data-ttu-id="56269-108">若要从某个程序按索引引用 LockFromGroupFormat 单元格，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="56269-108">To refer to the LockFromGroupFormat cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="56269-109">内容索引：</span><span class="sxs-lookup"><span data-stu-id="56269-109">Section index:</span></span>  <br/> |<span data-ttu-id="56269-110">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="56269-110">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="56269-111">行索引：</span><span class="sxs-lookup"><span data-stu-id="56269-111">Row index:</span></span>  <br/> |<span data-ttu-id="56269-112">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="56269-112">**visRowLock**</span></span> <br/> |
|<span data-ttu-id="56269-113">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="56269-113">Cell index:</span></span>  <br/> |<span data-ttu-id="56269-114">**visLockFromGroupFormat**</span><span class="sxs-lookup"><span data-stu-id="56269-114">**visLockFromGroupFormat**</span></span> <br/> |
   
<span data-ttu-id="56269-115">该单元格的默认值为 0 (False)。</span><span class="sxs-lookup"><span data-stu-id="56269-115">The default value for the cell is 0 (False).</span></span>
  

