---
title: LockFromGroupFormat 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: abd175af-ad4e-b84a-2687-2c9358653499
ms.openlocfilehash: 95633ab7a4127564fef65062bcf328d4364ebd86
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780637"
---
# <a name="lockfromgroupformat-cell-protection-section"></a><span data-ttu-id="f87d3-102">LockFromGroupFormat 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="f87d3-102">LockFromGroupFormat Cell (Protection Section)</span></span>

<span data-ttu-id="f87d3-103">阻止格式更改向组合形状被传播到及其子形状，同时仍允许用户直接设置所选的子形状的格式。</span><span class="sxs-lookup"><span data-stu-id="f87d3-103">Blocks format changes to a group shape from being propagated to its sub-shapes, while still allowing users to format selected sub-shapes directly.</span></span> 
  
<span data-ttu-id="f87d3-104">LockFromGroupFormat 单元格的值对应于**保护**对话框中的**从组格式**复选框设置。</span><span class="sxs-lookup"><span data-stu-id="f87d3-104">The value of the LockFromGroupFormat cell corresponds to the **From group formatting** check box setting in the **Protection** dialog box.</span></span> 
  
<span data-ttu-id="f87d3-105">若要引用 LockFromGroupFormat 单元格按名称从另一个公式或从使用**CellsU**属性的某个程序使用：</span><span class="sxs-lookup"><span data-stu-id="f87d3-105">To refer to the LockFromGroupFormat cell by name from another formula, or from a program, using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f87d3-106">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f87d3-106">Cell name:</span></span>  <br/> |<span data-ttu-id="f87d3-107">LockFromGroupFormat</span><span class="sxs-lookup"><span data-stu-id="f87d3-107">LockFromGroupFormat</span></span>  <br/> |
   
<span data-ttu-id="f87d3-108">要引用 LockFromGroupFormat 单元格的索引从某个程序，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="f87d3-108">To refer to the LockFromGroupFormat cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f87d3-109">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f87d3-109">Section index:</span></span>  <br/> |<span data-ttu-id="f87d3-110">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f87d3-110">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="f87d3-111">行索引：</span><span class="sxs-lookup"><span data-stu-id="f87d3-111">Row index:</span></span>  <br/> |<span data-ttu-id="f87d3-112">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="f87d3-112">**visRowLock**</span></span> <br/> |
|<span data-ttu-id="f87d3-113">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f87d3-113">Cell index:</span></span>  <br/> |<span data-ttu-id="f87d3-114">**visLockFromGroupFormat**</span><span class="sxs-lookup"><span data-stu-id="f87d3-114">**visLockFromGroupFormat**</span></span> <br/> |
   
<span data-ttu-id="f87d3-115">该单元格的默认值为 0 (False)。</span><span class="sxs-lookup"><span data-stu-id="f87d3-115">The default value for the cell is 0 (False).</span></span>
  

