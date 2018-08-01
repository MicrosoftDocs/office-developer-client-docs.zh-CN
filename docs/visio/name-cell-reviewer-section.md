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
ms.openlocfilehash: 6bc1629c51fc4dcb3fe7e2d6576e8f1f096144ae
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780786"
---
# <a name="name-cell-reviewer-section"></a><span data-ttu-id="4ae56-103">Name 单元格（“Reviewer”部分）</span><span class="sxs-lookup"><span data-stu-id="4ae56-103">Name Cell (Reviewer Section)</span></span>

<span data-ttu-id="4ae56-104">包含文档审阅者的姓名。</span><span class="sxs-lookup"><span data-stu-id="4ae56-104">Contains the name of a document reviewer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4ae56-105">注解</span><span class="sxs-lookup"><span data-stu-id="4ae56-105">Remarks</span></span>

 <span data-ttu-id="4ae56-106">该值默认为**Visio 选项**对话框的**常规**选项卡上的**用户名**框中找到的名称 （单击**文件**选项卡，单击**选项**，然后单击**常规**）。</span><span class="sxs-lookup"><span data-stu-id="4ae56-106">This value defaults to the name found in the **User name** box on the **General** tab of the **Visio Options** dialog box (click the **File** tab, click **Options**, and then click **General**).</span></span> 
  
<span data-ttu-id="4ae56-107">若要获取对 Name 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="4ae56-107">To get a reference to the Name cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4ae56-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4ae56-108">Cell name:</span></span>  <br/> | <span data-ttu-id="4ae56-109">Reviewer.Name [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="4ae56-109">Reviewer.Name [  *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="4ae56-110">若要从某个程序按索引获取对 Name 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4ae56-110">To get a reference to the Name cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4ae56-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4ae56-111">Section index:</span></span>  <br/> |<span data-ttu-id="4ae56-112">**visSectionReviewer**</span><span class="sxs-lookup"><span data-stu-id="4ae56-112">**visSectionReviewer**</span></span> <br/> |
| <span data-ttu-id="4ae56-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="4ae56-113">Row index:</span></span>  <br/> |<span data-ttu-id="4ae56-114">**visRowReviewer** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="4ae56-114">**visRowReviewer** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="4ae56-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4ae56-115">Cell index:</span></span>  <br/> |<span data-ttu-id="4ae56-116">**visReviewerName**</span><span class="sxs-lookup"><span data-stu-id="4ae56-116">**visReviewerName**</span></span> <br/> |
   

