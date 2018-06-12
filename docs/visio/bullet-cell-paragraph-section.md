---
title: Bullet 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm130
localization_priority: Normal
ms.assetid: 124a5ee1-6dd1-d17d-6f0e-dbaa5d95d9cd
description: 确定项目符号的样式。
ms.openlocfilehash: d3ecdd8e0f3780490f92766351b5ac94e875ae28
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779810"
---
# <a name="bullet-cell-paragraph-section"></a><span data-ttu-id="76d4c-103">Bullet 单元格（“Paragraph”内容）</span><span class="sxs-lookup"><span data-stu-id="76d4c-103">Bullet Cell (Paragraph Section)</span></span>

<span data-ttu-id="76d4c-104">确定项目符号的样式。</span><span class="sxs-lookup"><span data-stu-id="76d4c-104">Determines the bullet style.</span></span>
  
|<span data-ttu-id="76d4c-105">**值**</span><span class="sxs-lookup"><span data-stu-id="76d4c-105">**Value**</span></span>|<span data-ttu-id="76d4c-106">**项目符号样式**</span><span class="sxs-lookup"><span data-stu-id="76d4c-106">**Bullet style**</span></span>|
|:-----|:-----|
|<span data-ttu-id="76d4c-107">0</span><span class="sxs-lookup"><span data-stu-id="76d4c-107">0</span></span>  <br/> |<span data-ttu-id="76d4c-108">无</span><span class="sxs-lookup"><span data-stu-id="76d4c-108">None</span></span>  <br/> |
|<span data-ttu-id="76d4c-109">1</span><span class="sxs-lookup"><span data-stu-id="76d4c-109">1</span></span>  <br/> |![](media/IC_Bullet1_ZA07645847.gif)           <br/> |
|<span data-ttu-id="76d4c-110">2</span><span class="sxs-lookup"><span data-stu-id="76d4c-110">2</span></span>  <br/> |![](media/IC_Bullet2_ZA07645848.gif)           <br/> |
|<span data-ttu-id="76d4c-111">3</span><span class="sxs-lookup"><span data-stu-id="76d4c-111">3</span></span>  <br/> |![](media/IC_Bullet3_ZA07645849.gif)           <br/> |
|<span data-ttu-id="76d4c-112">4</span><span class="sxs-lookup"><span data-stu-id="76d4c-112">4</span></span>  <br/> |![](media/IC_Bullet4_ZA07645851.gif)           <br/> |
|<span data-ttu-id="76d4c-113">5</span><span class="sxs-lookup"><span data-stu-id="76d4c-113">5</span></span>  <br/> |![](media/IC_Bullet5_ZA07645852.gif)           <br/> |
|<span data-ttu-id="76d4c-114">6</span><span class="sxs-lookup"><span data-stu-id="76d4c-114">6</span></span>  <br/> |![](media/IC_Bullet6_ZA07645853.gif)           <br/> |
|<span data-ttu-id="76d4c-115">7</span><span class="sxs-lookup"><span data-stu-id="76d4c-115">7</span></span>  <br/> |![](media/IC_Bullet7_ZA07645854.gif)           <br/> |
   
|||
|:-----|:-----|
|<span data-ttu-id="76d4c-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="76d4c-116">Section index:</span></span>  <br/> |<span data-ttu-id="76d4c-117">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="76d4c-117">**visSectionParagraph**</span></span> <br/> |
|<span data-ttu-id="76d4c-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="76d4c-118">Row index:</span></span>  <br/> |<span data-ttu-id="76d4c-119">**visRowParagraph** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="76d4c-119">**visRowParagraph** +  *i*           where  *i*  = 0, 1, 2, ...</span></span>  <br/> |
|<span data-ttu-id="76d4c-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="76d4c-120">Cell index:</span></span>  <br/> |<span data-ttu-id="76d4c-121">**visBulletIndex**</span><span class="sxs-lookup"><span data-stu-id="76d4c-121">**visBulletIndex**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="76d4c-122">备注</span><span class="sxs-lookup"><span data-stu-id="76d4c-122">Remarks</span></span>

<span data-ttu-id="76d4c-123">您还可以设置此单元格的值右键单击形状，指向**格式**，单击**文本**，然后单击**项目符号**选项卡。</span><span class="sxs-lookup"><span data-stu-id="76d4c-123">You can also set the value of this cell by right-clicking a shape, pointing to **Format**, clicking **Text**, and then clicking the **Bullets** tab.</span></span> 
  
<span data-ttu-id="76d4c-124">若要获取对 Bullet 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="76d4c-124">To get a reference to the Bullet cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="76d4c-125">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="76d4c-125">Cell name:</span></span>  <br/> |<span data-ttu-id="76d4c-126">Para.Bullet [ *i* ] 其中*i* = < 1 >，2，3，...</span><span class="sxs-lookup"><span data-stu-id="76d4c-126">Para.Bullet[ *i*  ]           where  *i*  = <1>, 2, 3, ...</span></span>  <br/> |
   
<span data-ttu-id="76d4c-127">若要从某个程序按索引获取对 Bullet 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="76d4c-127">To get a reference to the Bullet cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  

