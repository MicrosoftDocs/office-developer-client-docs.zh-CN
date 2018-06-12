---
title: Initials 单元格（“Reviewer”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60045
localization_priority: Normal
ms.assetid: 8f5d34f0-4c4b-5265-83c1-5b86b73d464f
description: 包含文档审阅者的姓名首字母缩写。
ms.openlocfilehash: 65f0082219c8d6adca55af86c027b2ec5642fb5d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780465"
---
# <a name="initials-cell-reviewer-section"></a><span data-ttu-id="09f65-103">Initials 单元格（“Reviewer”内容）</span><span class="sxs-lookup"><span data-stu-id="09f65-103">Initials Cell (Reviewer Section)</span></span>

<span data-ttu-id="09f65-104">包含文档审阅者的姓名首字母缩写。</span><span class="sxs-lookup"><span data-stu-id="09f65-104">Contains the initials of a document reviewer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="09f65-105">注解</span><span class="sxs-lookup"><span data-stu-id="09f65-105">Remarks</span></span>

<span data-ttu-id="09f65-106">该值默认为**Visio 选项**对话框中**常规**选项卡上**缩写**框中的缩写 （单击**文件**选项卡，单击**选项**，然后单击**常规**）。</span><span class="sxs-lookup"><span data-stu-id="09f65-106">This value defaults to the initials in the **Initials** box on the **General** tab in the **Visio Options** dialog box (click the **File** tab, click **Options**, and then click **General** ).</span></span> 
  
<span data-ttu-id="09f65-107">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Initials 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="09f65-107">To get a reference to the Initials cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="09f65-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="09f65-108">Cell name:</span></span>  <br/> | <span data-ttu-id="09f65-109">Reviewer.Initials [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="09f65-109">Reviewer.Initials [  *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="09f65-110">若要从某个程序按索引获取对 Initials 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="09f65-110">To get a reference to the Initials cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="09f65-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="09f65-111">Section index:</span></span>  <br/> |<span data-ttu-id="09f65-112">**visSectionReviewer**</span><span class="sxs-lookup"><span data-stu-id="09f65-112">**visSectionReviewer**</span></span> <br/> |
| <span data-ttu-id="09f65-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="09f65-113">Row index:</span></span>  <br/> |<span data-ttu-id="09f65-114">**visRowReviewer** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="09f65-114">**visRowReviewer** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="09f65-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="09f65-115">Cell index:</span></span>  <br/> |<span data-ttu-id="09f65-116">**visReviewerInitials**</span><span class="sxs-lookup"><span data-stu-id="09f65-116">**visReviewerInitials**</span></span> <br/> |
   

