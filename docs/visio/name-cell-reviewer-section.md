---
title: Name 单元格（“Reviewer”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1030992
localization_priority: Normal
ms.assetid: be39cd0b-56bf-a070-f5d8-c9a440d81ee2
description: 包含文档审阅者的姓名。
ms.openlocfilehash: 02f353ab8f2d39cc075211bb13157b93081e9d8f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417684"
---
# <a name="name-cell-reviewer-section"></a><span data-ttu-id="7ccc4-103">Name 单元格（“Reviewer”内容）</span><span class="sxs-lookup"><span data-stu-id="7ccc4-103">Name Cell (Reviewer Section)</span></span>

<span data-ttu-id="7ccc4-104">包含文档审阅者的姓名。</span><span class="sxs-lookup"><span data-stu-id="7ccc4-104">Contains the name of a document reviewer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7ccc4-105">备注</span><span class="sxs-lookup"><span data-stu-id="7ccc4-105">Remarks</span></span>

 <span data-ttu-id="7ccc4-106">此值默认为在"Visio 选项"对话框的"常规"选项卡上的"用户名"框中找到的名称 (单击"文件"选项卡，单击"选项"，然后单击"常规) "。  </span><span class="sxs-lookup"><span data-stu-id="7ccc4-106">This value defaults to the name found in the **User name** box on the **General** tab of the **Visio Options** dialog box (click the **File** tab, click **Options**, and then click **General**).</span></span> 
  
<span data-ttu-id="7ccc4-107">若要从另一个公式或使用 **CellsU** 属性从程序按名称获取对 Name 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7ccc4-107">To get a reference to the Name cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7ccc4-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7ccc4-108">Cell name:</span></span>  <br/> | <span data-ttu-id="7ccc4-109">Reviewer.Name [  *i*  ] 其中  *i*  = <1> 2， 3...</span><span class="sxs-lookup"><span data-stu-id="7ccc4-109">Reviewer.Name [  *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="7ccc4-110">若要从某个程序按索引获取对 Name 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7ccc4-110">To get a reference to the Name cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7ccc4-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7ccc4-111">Section index:</span></span>  <br/> |<span data-ttu-id="7ccc4-112">**visSectionReviewer**</span><span class="sxs-lookup"><span data-stu-id="7ccc4-112">**visSectionReviewer**</span></span> <br/> |
| <span data-ttu-id="7ccc4-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="7ccc4-113">Row index:</span></span>  <br/> |<span data-ttu-id="7ccc4-114">**visRowReviewer**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="7ccc4-114">**visRowReviewer** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="7ccc4-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7ccc4-115">Cell index:</span></span>  <br/> |<span data-ttu-id="7ccc4-116">**visReviewerName**</span><span class="sxs-lookup"><span data-stu-id="7ccc4-116">**visReviewerName**</span></span> <br/> |
   

