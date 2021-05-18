---
title: BulletSize 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033780
localization_priority: Normal
ms.assetid: 6ff5d07b-17e2-f6ca-1860-5d498a9ebf06
description: 指定项目符号的大小。
ms.openlocfilehash: 8671bc6f5ec40814b13727bc458f74eb2893f839
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405420"
---
# <a name="bulletsize-cell-paragraph-section"></a><span data-ttu-id="1704e-103">BulletSize 单元格（“Paragraph”内容）</span><span class="sxs-lookup"><span data-stu-id="1704e-103">BulletSize Cell (Paragraph Section)</span></span>

<span data-ttu-id="1704e-104">指定项目符号的大小。</span><span class="sxs-lookup"><span data-stu-id="1704e-104">Specifies the size of a bullet.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="1704e-105">备注</span><span class="sxs-lookup"><span data-stu-id="1704e-105">Remarks</span></span>

<span data-ttu-id="1704e-106">可为预定义项目符号或自定义项目符号指定此值，该值可以是百分比值也可以是具体的值。</span><span class="sxs-lookup"><span data-stu-id="1704e-106">This value can be specified for either predefined or custom bullets, as either a percentage or a specific value.</span></span> 
  
<span data-ttu-id="1704e-107">如果值为零 (0) ，则项目符号的字体大小与段落中第一个字符的字体大小相同。</span><span class="sxs-lookup"><span data-stu-id="1704e-107">If the value is zero (0), the bullet is the same font size as that of the first character in the paragraph.</span></span> <span data-ttu-id="1704e-108">如果该值是百分比，则项目符号的字体大小是段落中第一个字符大小的相应百分比。</span><span class="sxs-lookup"><span data-stu-id="1704e-108">If the value is a percentage, the bullet is sized as a percentage of the font size of the first character in the paragraph.</span></span> <span data-ttu-id="1704e-109">负数将视为百分比。</span><span class="sxs-lookup"><span data-stu-id="1704e-109">Negative numbers are treated as percentages.</span></span>
  
<span data-ttu-id="1704e-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 BulletSize 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="1704e-110">To get a reference to the BulletSize cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1704e-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1704e-111">Cell name:</span></span>  <br/> | <span data-ttu-id="1704e-112">Para.BulletFontSize[  *i*  ] 其中  *i*  = <1>， 2， 3...</span><span class="sxs-lookup"><span data-stu-id="1704e-112">Para.BulletFontSize[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="1704e-113">要从某个程序按索引获取对 BulletSize 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="1704e-113">To get a reference to the BulletSize cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1704e-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1704e-114">Section index:</span></span>  <br/> |<span data-ttu-id="1704e-115">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="1704e-115">**visSectionParagraph**</span></span> <br/> |
| <span data-ttu-id="1704e-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="1704e-116">Row index:</span></span>  <br/> |<span data-ttu-id="1704e-117">**visRowParagraph**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="1704e-117">**visRowParagraph** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="1704e-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1704e-118">Cell index:</span></span>  <br/> |<span data-ttu-id="1704e-119">**visBulletFontSize**</span><span class="sxs-lookup"><span data-stu-id="1704e-119">**visBulletFontSize**</span></span> <br/> |
   

