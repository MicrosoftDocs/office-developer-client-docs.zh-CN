---
title: ComplexScriptSize 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033768
localization_priority: Normal
ms.assetid: f58687d7-2ba4-ff77-0bcc-3106867d89de
description: 用于设置由复杂文种字符组成的文字的格式的字号。
ms.openlocfilehash: 38b01c4a0142c7eca2923ee9b13963eaa1a62830
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428436"
---
# <a name="complexscriptsize-cell-character-section"></a><span data-ttu-id="c3704-103">ComplexScriptSize 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="c3704-103">ComplexScriptSize Cell (Character Section)</span></span>

<span data-ttu-id="c3704-104">用于设置由复杂文种字符组成的文字的格式的字号。</span><span class="sxs-lookup"><span data-stu-id="c3704-104">The size of the font used to format text composed of complex script characters.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c3704-105">备注</span><span class="sxs-lookup"><span data-stu-id="c3704-105">Remarks</span></span>

<span data-ttu-id="c3704-106">复杂脚本字体大小列在"文本"对话框的"字体"选项卡上 (单击"开始"选项卡上"字体"组中) 。  </span><span class="sxs-lookup"><span data-stu-id="c3704-106">Complex script font sizes are listed on the **Font** tab in the **Text** dialog box (click the arrow in the **Font** group on the **Home** tab).</span></span> <span data-ttu-id="c3704-107">只有在"语言首选项"对话框中添加了包含亚洲语言或复杂脚本字符 **Microsoft Office，** 此列表才显示。</span><span class="sxs-lookup"><span data-stu-id="c3704-107">This list appears only if you have added a language that contains Asian or complex script characters, in the **Microsoft Office Language Preferences** dialog box.</span></span> <span data-ttu-id="c3704-108"> (**单击开始**，单击所有 **程序，Microsoft Office，** 单击Microsoft Office **工具**，然后单击Microsoft Office **语言首选项。**</span><span class="sxs-lookup"><span data-stu-id="c3704-108">(Click **Start**, click **All Programs**, click **Microsoft Office**, click **Microsoft Office Tools**, and then click **Microsoft Office Language Preferences**.</span></span>
  
<span data-ttu-id="c3704-p102">您可以为此值输入明确的磅值或百分比。如果指定某一百分比，则该值将基于 Size 单元格中的值。默认值 0（零）表示 100%。</span><span class="sxs-lookup"><span data-stu-id="c3704-p102">You can enter this value as an explicit point size or as a percentage. If you specify a percentage, the value is based on the value in the Size cell. A default value of 0 (zero) means 100%.</span></span> 
  
<span data-ttu-id="c3704-112">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ComplexScriptSize 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c3704-112">To get a reference to the ComplexScriptSize cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c3704-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c3704-113">Cell name:</span></span>  <br/> |<span data-ttu-id="c3704-114">Char.ComplexScriptSize[ *i*  ] 其中  *i*  = <1> 2， 3...</span><span class="sxs-lookup"><span data-stu-id="c3704-114">Char.ComplexScriptSize[ *i*  ]           where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="c3704-115">若要从某个程序按索引获取对 ComplexScriptSize 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c3704-115">To get a reference to the ComplexScriptSize cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c3704-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c3704-116">Section index:</span></span>  <br/> |<span data-ttu-id="c3704-117">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="c3704-117">**visSectionCharacter**</span></span> <br/> |
|<span data-ttu-id="c3704-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="c3704-118">Row index:</span></span>  <br/> |<span data-ttu-id="c3704-119">**visRowCharacter**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="c3704-119">**visRowCharacter** +  *i*           where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="c3704-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c3704-120">Cell index:</span></span>  <br/> |<span data-ttu-id="c3704-121">**visCharacterComplexScriptSize**</span><span class="sxs-lookup"><span data-stu-id="c3704-121">**visCharacterComplexScriptSize**</span></span> <br/> |
   

