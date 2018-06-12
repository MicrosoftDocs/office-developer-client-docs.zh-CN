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
ms.openlocfilehash: 1fbaa0b27a0c639519c302129142dcefe5708115
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779647"
---
# <a name="asianfont-cell-character-section"></a><span data-ttu-id="60190-104">AsianFont 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="60190-104">AsianFont Cell (Character Section)</span></span>

<span data-ttu-id="60190-p102">包含用于设置含有亚洲字符的文字格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。</span><span class="sxs-lookup"><span data-stu-id="60190-p102">Contains the number of the font used to format the text containing Asian characters. Font numbers vary according to the fonts installed on your system.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="60190-107">注解</span><span class="sxs-lookup"><span data-stu-id="60190-107">Remarks</span></span>

<span data-ttu-id="60190-108">**文本**对话框 （单击**主页**选项卡组的**字体**箭头） 中的**字体**选项卡上列出亚洲字体。</span><span class="sxs-lookup"><span data-stu-id="60190-108">Asian fonts are listed on the **Font** tab in the **Text** dialog box (click the arrow in the **Font** group on the **Home** tab).</span></span> <span data-ttu-id="60190-109">仅当您已添加了包含用于亚洲语言或复杂文种字符，在**Microsoft Office 语言首选项**对话框中的语言，将显示此列表。</span><span class="sxs-lookup"><span data-stu-id="60190-109">This list appears only if you have added a language that contains Asian or complex script characters, in the **Microsoft Office Language Preferences** dialog box.</span></span> <span data-ttu-id="60190-110">（单击**开始**，单击**所有程序**，都单击**Microsoft Office**、 都单击**Microsoft Office 工具**，然后都单击**Microsoft Office 语言首选项**。</span><span class="sxs-lookup"><span data-stu-id="60190-110">(Click **Start**, click **All Programs**, click **Microsoft Office**, click **Microsoft Office Tools**, and then click **Microsoft Office Language Preferences**.</span></span>
  
<span data-ttu-id="60190-p104">数字 0 表示未指定任何字体。如果西文字体或默认字体含有必需的字符，那么将使用这些字体。</span><span class="sxs-lookup"><span data-stu-id="60190-p104">The number 0 means no font is specified. The Latin font or default fonts are used if they contain the necessary characters.</span></span>
  
<span data-ttu-id="60190-113">若要获取对 AsianFont 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="60190-113">To get a reference to the AsianFont cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="60190-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="60190-114">Cell name:</span></span>  <br/> |<span data-ttu-id="60190-115">Char.AsianFont [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="60190-115">Char.AsianFont[ *i*  ]           where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="60190-116">若要从某个程序按索引获取对 AsianFont 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="60190-116">To get a reference to the AsianFont cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="60190-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="60190-117">Section index:</span></span>  <br/> |<span data-ttu-id="60190-118">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="60190-118">**visSectionCharacter**</span></span> <br/> |
|<span data-ttu-id="60190-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="60190-119">Row index:</span></span>  <br/> |<span data-ttu-id="60190-120">**visRowCharacter** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="60190-120">**visRowCharacter** +  *i*           where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="60190-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="60190-121">Cell index:</span></span>  <br/> |<span data-ttu-id="60190-122">**visCharacterAsianFont**</span><span class="sxs-lookup"><span data-stu-id="60190-122">**visCharacterAsianFont**</span></span> <br/> |
   

