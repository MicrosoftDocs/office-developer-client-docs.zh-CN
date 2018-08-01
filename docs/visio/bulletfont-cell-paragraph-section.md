---
title: BulletFont 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60023
localization_priority: Normal
ms.assetid: a75ff1f3-2f4d-89e3-108b-e16a34f5184f
description: 表示当指定了自定义项目符号字符串并且 Bullet 单元格中的值不为零时，用于设置文字格式的字体编号。
ms.openlocfilehash: 7cd3333afc30d30ea7b0e5d35650681074744235
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779819"
---
# <a name="bulletfont-cell-paragraph-section"></a><span data-ttu-id="cf355-103">BulletFont 单元格（“Paragraph”部分）</span><span class="sxs-lookup"><span data-stu-id="cf355-103">BulletFont Cell (Paragraph Section)</span></span>

<span data-ttu-id="cf355-104">表示当指定了自定义项目符号字符串并且 Bullet 单元格中的值不为零时，用于设置文字格式的字体编号。</span><span class="sxs-lookup"><span data-stu-id="cf355-104">Represents the number of the font used to format the text when a custom bullet string is specified and the value in the Bullet cell is non-zero.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="cf355-105">注释</span><span class="sxs-lookup"><span data-stu-id="cf355-105">Remarks</span></span>

<span data-ttu-id="cf355-p101">根据您的系统上安装的字体，字体编号会有所不同。如果该值是 0 并且有自定义项目符号字符串，则所使用的字体与该段落的第一个字符的字体相同。</span><span class="sxs-lookup"><span data-stu-id="cf355-p101">Font numbers vary according to the fonts installed on your system. If the value is 0 and there is a custom bullet string, the font used is the same as the font of the first character of the paragraph.</span></span>
  
<span data-ttu-id="cf355-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 BulletFont 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="cf355-108">To get a reference to the BulletFont cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cf355-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cf355-109">Cell name:</span></span>  <br/> | <span data-ttu-id="cf355-110">Para.BulletFont [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="cf355-110">Para.BulletFont[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="cf355-111">要从某个程序按索引获取对 BulletFont 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="cf355-111">To get a reference to the BulletFont cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cf355-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cf355-112">Section index:</span></span>  <br/> |<span data-ttu-id="cf355-113">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="cf355-113">**visSectionParagraph**</span></span> <br/> |
| <span data-ttu-id="cf355-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="cf355-114">Row index:</span></span>  <br/> |<span data-ttu-id="cf355-115">**visRowParagraph** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="cf355-115">**visRowParagraph** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="cf355-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cf355-116">Cell index:</span></span>  <br/> |<span data-ttu-id="cf355-117">**visBulletFont**</span><span class="sxs-lookup"><span data-stu-id="cf355-117">**visBulletFont**</span></span> <br/> |
   

