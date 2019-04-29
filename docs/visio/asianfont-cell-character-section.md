---
title: AsianFont 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033764
localization_priority: Normal
ms.assetid: 45bfaaaa-52cc-f8b4-68e7-8b99e5788ce1
description: 包含用于设置含有亚洲字符的文字格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。
ms.openlocfilehash: 4af7e590a7bd0733ad622f3df259aa6c01837c4b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406589"
---
# <a name="asianfont-cell-character-section"></a><span data-ttu-id="dba6d-104">AsianFont 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="dba6d-104">AsianFont Cell (Character Section)</span></span>

<span data-ttu-id="dba6d-p102">包含用于设置含有亚洲字符的文字格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。</span><span class="sxs-lookup"><span data-stu-id="dba6d-p102">Contains the number of the font used to format the text containing Asian characters. Font numbers vary according to the fonts installed on your system.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="dba6d-107">说明</span><span class="sxs-lookup"><span data-stu-id="dba6d-107">Remarks</span></span>

<span data-ttu-id="dba6d-p103">亚洲字体在 **“文本”** 对话框中的 **“字体”** 选项卡（单击 **“开始”** 选项卡上的 **“字体”** 组中的箭头）上列出。只有在 **“Microsoft Office 语言首选项”** 对话框（依次单击 **“开始”**、**“所有程序”**、**“Microsoft Office”**、**“Microsoft Office 工具”** 和 **“Microsoft Office 语言首选项”**）中添加了包含亚洲或复杂文种字符的语言后，才会显示此列表。</span><span class="sxs-lookup"><span data-stu-id="dba6d-p103">Asian fonts are listed on the **Font** tab in the **Text** dialog box (click the arrow in the **Font** group on the **Home** tab). This list appears only if you have added a language that contains Asian or complex script characters, in the **Microsoft Office Language Preferences** dialog box. (Click **Start**, click **All Programs**, click **Microsoft Office**, click **Microsoft Office Tools**, and then click **Microsoft Office Language Preferences**.</span></span>
  
<span data-ttu-id="dba6d-p104">数字 0 表示未指定任何字体。如果西文字体或默认字体含有必需的字符，那么将使用这些字体。</span><span class="sxs-lookup"><span data-stu-id="dba6d-p104">The number 0 means no font is specified. The Latin font or default fonts are used if they contain the necessary characters.</span></span>
  
<span data-ttu-id="dba6d-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 AsianFont 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="dba6d-113">To get a reference to the AsianFont cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dba6d-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="dba6d-114">Cell name:</span></span>  <br/> |<span data-ttu-id="dba6d-115">AsianFont [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="dba6d-115">Char.AsianFont[ *i*  ]           where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="dba6d-116">若要从某个程序按索引获取对 AsianFont 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="dba6d-116">To get a reference to the AsianFont cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dba6d-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="dba6d-117">Section index:</span></span>  <br/> |<span data-ttu-id="dba6d-118">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="dba6d-118">**visSectionCharacter**</span></span> <br/> |
|<span data-ttu-id="dba6d-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="dba6d-119">Row index:</span></span>  <br/> |<span data-ttu-id="dba6d-120">**visRowCharacter** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="dba6d-120">**visRowCharacter** +  *i*           where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="dba6d-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="dba6d-121">Cell index:</span></span>  <br/> |<span data-ttu-id="dba6d-122">**visCharacterAsianFont**</span><span class="sxs-lookup"><span data-stu-id="dba6d-122">**visCharacterAsianFont**</span></span> <br/> |
   

