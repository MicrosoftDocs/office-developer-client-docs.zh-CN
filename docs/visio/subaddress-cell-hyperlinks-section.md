---
title: SubAddress 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm985
localization_priority: Normal
ms.assetid: 949448fd-0f85-b56a-945e-1da0e48609e8
description: 指定要链接到的目标文档内的位置。
ms.openlocfilehash: 0509b9b6a708924b5aeb69f16f3f4cd99573cc0c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781464"
---
# <a name="subaddress-cell-hyperlinks-section"></a><span data-ttu-id="543b5-103">SubAddress 单元格（“Hyperlinks”内容）</span><span class="sxs-lookup"><span data-stu-id="543b5-103">SubAddress Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="543b5-104">指定要链接到的目标文档内的位置。</span><span class="sxs-lookup"><span data-stu-id="543b5-104">Specifies a location within the target document to link to.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="543b5-105">注解</span><span class="sxs-lookup"><span data-stu-id="543b5-105">Remarks</span></span>

<span data-ttu-id="543b5-106">例如，如果 Address 单元格，"Drawing1.vsdx"SubAddress 单元格可以指定一个页面名称，例如"第 3 页"。</span><span class="sxs-lookup"><span data-stu-id="543b5-106">For example, if the Address cell is "Drawing1.vsdx", the SubAddress cell can specify a page name such as "Page-3".</span></span> <span data-ttu-id="543b5-107">如果 Address 单元格，Microsoft Excel 文件"Samples.xlsx"此单元格值可以是工作表或工作表，如"工作表函数"或"Sheet1 中范围 ！A1: D10"。</span><span class="sxs-lookup"><span data-stu-id="543b5-107">If the Address cell is the Microsoft Excel file "Samples.xlsx", the value of this cell can be a worksheet or range within a worksheet, such as "Worksheet Functions" or "Sheet1!A1:D10".</span></span> <span data-ttu-id="543b5-108">Address 单元格是否"http://www.microsoft.com/office/"，此单元格的值可以是在文档中，例如"解决方案"命名的定位。</span><span class="sxs-lookup"><span data-stu-id="543b5-108">If the Address cell is "http://www.microsoft.com/office/", the value of this cell can be a named anchor within the document, such as "solutions".</span></span>
  
<span data-ttu-id="543b5-109">您还可以在**超链接**对话框中设置此单元格的值 （在**插入**选项卡上的**链接**组中，单击**超链接**）。</span><span class="sxs-lookup"><span data-stu-id="543b5-109">You can also set the value of this cell in the **Hyperlinks** dialog box (in the **Links** group on the **Insert** tab, click **Hyperlink**).</span></span>
  
<span data-ttu-id="543b5-110">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 SubAddress 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="543b5-110">To get a reference to the SubAddress cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="543b5-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="543b5-111">Cell name:</span></span>  <br/> | <span data-ttu-id="543b5-112">超链接。</span><span class="sxs-lookup"><span data-stu-id="543b5-112">Hyperlink.</span></span>  <span data-ttu-id="543b5-113">*名称*。SubAddress 其中超链接 *.name*是行名称</span><span class="sxs-lookup"><span data-stu-id="543b5-113">*name*  .SubAddress where Hyperlink  *.name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="543b5-114">若要从某个程序按索引获取对**SubAddress**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="543b5-114">To get a reference to the **SubAddress** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="543b5-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="543b5-115">Section index:</span></span>  <br/> |<span data-ttu-id="543b5-116">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="543b5-116">**visSectionHyperlink**</span></span> <br/> |
| <span data-ttu-id="543b5-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="543b5-117">Row index:</span></span>  <br/> |<span data-ttu-id="543b5-118">**visRow1stHyperlink** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="543b5-118">**visRow1stHyperlink** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="543b5-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="543b5-119">Cell index:</span></span>  <br/> |<span data-ttu-id="543b5-120">**visHLinkSubAddress**</span><span class="sxs-lookup"><span data-stu-id="543b5-120">**visHLinkSubAddress**</span></span> <br/> |
   

