---
title: Value 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1095
localization_priority: Normal
ms.assetid: 3ca662c8-1ce4-89a9-3264-1ba533fcd444
description: 包含域的函数。
ms.openlocfilehash: d5a09dd0d59341125db897484f74addff22328de
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320200"
---
# <a name="value-cell-text-fields-section"></a><span data-ttu-id="43312-103">Value 单元格（“Text Fields”内容）</span><span class="sxs-lookup"><span data-stu-id="43312-103">Value Cell (Text Fields Section)</span></span>

<span data-ttu-id="43312-104">包含域的函数。</span><span class="sxs-lookup"><span data-stu-id="43312-104">Contains the function for a field.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="43312-105">注解</span><span class="sxs-lookup"><span data-stu-id="43312-105">Remarks</span></span>

<span data-ttu-id="43312-106">您可以使用 **“域”** 对话框（在 **“插入”** 选项卡上的 **“文本”** 组中单击 **“域”**）设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="43312-106">You can set the value of this cell using the **Field** dialog box (on the **Insert** tab, in the **Text** group, click **Field**).</span></span>
  
<span data-ttu-id="43312-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Value 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="43312-107">To get a reference to the Value cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="43312-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="43312-108">Cell name:</span></span>  <br/> |<span data-ttu-id="43312-109">Fields 值 [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="43312-109">Fields.Value[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="43312-110">要从某个程序按索引获取对 Value 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="43312-110">To get a reference to the Value cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="43312-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="43312-111">Section index:</span></span>  <br/> |<span data-ttu-id="43312-112">**visSectionTextField**</span><span class="sxs-lookup"><span data-stu-id="43312-112">**visSectionTextField**</span></span> <br/> |
|<span data-ttu-id="43312-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="43312-113">Row index:</span></span>  <br/> |<span data-ttu-id="43312-114">**visRowField** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="43312-114">**visRowField** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="43312-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="43312-115">Cell index:</span></span>  <br/> |<span data-ttu-id="43312-116">**visFieldCell**</span><span class="sxs-lookup"><span data-stu-id="43312-116">**visFieldCell**</span></span> <br/> |
   

