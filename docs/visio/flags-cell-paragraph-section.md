---
title: Flags 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033782
localization_priority: Normal
ms.assetid: 898bf89d-d00f-9769-a89d-787ef708eca5
description: 指示文本方向是从左到右还是从右到左。
ms.openlocfilehash: b471d08556bedf68ce75595b9c211758297e8352
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780256"
---
# <a name="flags-cell-paragraph-section"></a><span data-ttu-id="21ebb-103">Flags 单元格（“Paragraph”部分）</span><span class="sxs-lookup"><span data-stu-id="21ebb-103">Flags Cell (Paragraph Section)</span></span>

<span data-ttu-id="21ebb-104">指示文本方向是从左到右还是从右到左。</span><span class="sxs-lookup"><span data-stu-id="21ebb-104">Indicates whether the text direction is left to right or right to left.</span></span>
  
|<span data-ttu-id="21ebb-105">**值**</span><span class="sxs-lookup"><span data-stu-id="21ebb-105">**Value**</span></span>|<span data-ttu-id="21ebb-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="21ebb-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="21ebb-107">0</span><span class="sxs-lookup"><span data-stu-id="21ebb-107">0</span></span>  <br/> |<span data-ttu-id="21ebb-108">文本方向从左到右（默认值）。</span><span class="sxs-lookup"><span data-stu-id="21ebb-108">The text direction is left to right (the default).</span></span>  <br/> |
|<span data-ttu-id="21ebb-109">1</span><span class="sxs-lookup"><span data-stu-id="21ebb-109">1</span></span>  <br/> |<span data-ttu-id="21ebb-110">文本方向从右到左。</span><span class="sxs-lookup"><span data-stu-id="21ebb-110">The text direction is right to left.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="21ebb-111">注解</span><span class="sxs-lookup"><span data-stu-id="21ebb-111">Remarks</span></span>

<span data-ttu-id="21ebb-112">此单元格中的值对应于**文本**对话框中的**段落**选项卡上的**方向**设置 （在**主页**选项卡上，单击**字体**箭头），其中显示仅当语言使用复杂文种文字已添加**Microsoft Office 语言首选项**对话框中。</span><span class="sxs-lookup"><span data-stu-id="21ebb-112">The value in this cell corresponds to the **Direction** setting on the **Paragraph** tab in the **Text** dialog box (on the **Home** tab, click the **Font** arrow), which appears only if a language that uses complex scripts text has been added in the **Microsoft Office Language Preferences** dialog box.</span></span> <span data-ttu-id="21ebb-113">（单击**开始**，单击**所有程序**，都单击**Microsoft Office**、 都单击**Microsoft Office 工具**，然后都单击**Microsoft Office 语言首选项**。）</span><span class="sxs-lookup"><span data-stu-id="21ebb-113">(Click **Start**, click **All Programs**, click **Microsoft Office**, click **Microsoft Office Tools**, and then click **Microsoft Office Language Preferences**.)</span></span> 
  
<span data-ttu-id="21ebb-114">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Flags 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="21ebb-114">To get a reference to the Flags cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="21ebb-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="21ebb-115">Cell name:</span></span>  <br/> |<span data-ttu-id="21ebb-116">Para.Flags [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="21ebb-116">Para.Flags[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="21ebb-117">若要从某个程序按索引获取对 Flags 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="21ebb-117">To get a reference to the Flags cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="21ebb-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="21ebb-118">Section index:</span></span>  <br/> |<span data-ttu-id="21ebb-119">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="21ebb-119">**visSectionParagraph**</span></span> <br/> |
|<span data-ttu-id="21ebb-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="21ebb-120">Row index:</span></span>  <br/> |<span data-ttu-id="21ebb-121">**visRowParagraph** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="21ebb-121">**visRowParagraph** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="21ebb-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="21ebb-122">Cell index:</span></span>  <br/> |<span data-ttu-id="21ebb-123">**visFlags**</span><span class="sxs-lookup"><span data-stu-id="21ebb-123">**visFlags**</span></span> <br/> |
   

