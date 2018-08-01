---
title: ComplexScriptFont 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60034
localization_priority: Normal
ms.assetid: e1cf9e97-101b-384f-65fe-0169c89dfccc
description: 包含用于设置由复杂文种字符组成的文字的格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。
ms.openlocfilehash: 0aae3a22be26f206763f18107eaced74f1078503
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779926"
---
# <a name="complexscriptfont-cell-character-section"></a><span data-ttu-id="23fbe-104">ComplexScriptFont 单元格（“Character”部分）</span><span class="sxs-lookup"><span data-stu-id="23fbe-104">ComplexScriptFont Cell (Character Section)</span></span>

<span data-ttu-id="23fbe-p102">包含用于设置由复杂文种字符组成的文字的格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。</span><span class="sxs-lookup"><span data-stu-id="23fbe-p102">Contains the number of the font used to format text composed of complex script characters. Font numbers vary according to the fonts installed on your system.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="23fbe-107">注解</span><span class="sxs-lookup"><span data-stu-id="23fbe-107">Remarks</span></span>

<span data-ttu-id="23fbe-108">**文本**对话框 （单击**主页**选项卡组的**字体**箭头） 中的**字体**选项卡上列出复杂文种字体大小。</span><span class="sxs-lookup"><span data-stu-id="23fbe-108">Complex script font sizes are listed on the **Font** tab in the **Text** dialog box (click the arrow in the **Font** group on the **Home** tab).</span></span> <span data-ttu-id="23fbe-109">仅当您已添加了包含用于亚洲语言或复杂文种字符，在**Microsoft Office 语言首选项**对话框中的语言，将显示此列表。</span><span class="sxs-lookup"><span data-stu-id="23fbe-109">This list appears only if you have added a language that contains Asian or complex script characters, in the **Microsoft Office Language Preferences** dialog box.</span></span> <span data-ttu-id="23fbe-110">（单击**开始**，单击**所有程序**，都单击**Microsoft Office**、 都单击**Microsoft Office 工具**，然后都单击**Microsoft Office 语言首选项**。</span><span class="sxs-lookup"><span data-stu-id="23fbe-110">(Click **Start**, click **All Programs**, click **Microsoft Office**, click **Microsoft Office Tools**, and then click **Microsoft Office Language Preferences**.</span></span>
  
<span data-ttu-id="23fbe-111">数字 0 （零） 表示未指定任何字体。</span><span class="sxs-lookup"><span data-stu-id="23fbe-111">The number 0 (zero) means no font is specified.</span></span> <span data-ttu-id="23fbe-112">使用西文字体或默认字体。</span><span class="sxs-lookup"><span data-stu-id="23fbe-112">The Latin font or default fonts are used.</span></span>
  
<span data-ttu-id="23fbe-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ComplexScriptSize 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="23fbe-113">To get a reference to the ComplexScriptSize cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="23fbe-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="23fbe-114">Cell name:</span></span>  <br/> |<span data-ttu-id="23fbe-115">Char.ComplexScriptFont [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="23fbe-115">Char.ComplexScriptFont[ *i*  ]           where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="23fbe-116">若要从某个程序按索引获取对 ComplexScriptFont 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="23fbe-116">To get a reference to the ComplexScriptFont cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="23fbe-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="23fbe-117">Section index:</span></span>  <br/> |<span data-ttu-id="23fbe-118">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="23fbe-118">**visSectionCharacter**</span></span> <br/> |
|<span data-ttu-id="23fbe-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="23fbe-119">Row index:</span></span>  <br/> |<span data-ttu-id="23fbe-120">**visRowCharacter** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="23fbe-120">**visRowCharacter** +  *i*           where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="23fbe-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="23fbe-121">Cell index:</span></span>  <br/> |<span data-ttu-id="23fbe-122">**visCharacterComplexScriptFont**</span><span class="sxs-lookup"><span data-stu-id="23fbe-122">**visCharacterComplexScriptFont**</span></span> <br/> |
   

