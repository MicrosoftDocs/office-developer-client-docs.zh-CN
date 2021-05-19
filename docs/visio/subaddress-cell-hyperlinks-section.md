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
ms.openlocfilehash: 092a53bd7c9d5adb77ed35f3e2ef53888bd6ebea
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349320"
---
# <a name="subaddress-cell-hyperlinks-section"></a><span data-ttu-id="30223-103">SubAddress 单元格（“Hyperlinks”内容）</span><span class="sxs-lookup"><span data-stu-id="30223-103">SubAddress Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="30223-104">指定要链接到的目标文档内的位置。</span><span class="sxs-lookup"><span data-stu-id="30223-104">Specifies a location within the target document to link to.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="30223-105">备注</span><span class="sxs-lookup"><span data-stu-id="30223-105">Remarks</span></span>

<span data-ttu-id="30223-106">例如，如果 Address 单元格为"Drawing1.vsdx"，则 SubAddress 单元格可以指定页面名称，如"Page-3"。</span><span class="sxs-lookup"><span data-stu-id="30223-106">For example, if the Address cell is "Drawing1.vsdx", the SubAddress cell can specify a page name such as "Page-3".</span></span> <span data-ttu-id="30223-107">如果 Address 单元格是Microsoft Excel文件"Samples.xlsx"，则此单元格的值可以是工作表中的工作表或区域，例如"Worksheet Functions"或"Sheet1！A1：D10"。</span><span class="sxs-lookup"><span data-stu-id="30223-107">If the Address cell is the Microsoft Excel file "Samples.xlsx", the value of this cell can be a worksheet or range within a worksheet, such as "Worksheet Functions" or "Sheet1!A1:D10".</span></span> <span data-ttu-id="30223-108">如果 Address 单元格为""，则此单元格的值可以是文档中的命名定位标记， https://www.microsoft.com/office/ 例如"solutions"。</span><span class="sxs-lookup"><span data-stu-id="30223-108">If the Address cell is "https://www.microsoft.com/office/", the value of this cell can be a named anchor within the document, such as "solutions".</span></span>
  
<span data-ttu-id="30223-109">您还可以在 **“超链接”** 对话框（在 **“插入”** 选项卡上的 **“链接”** 组中，单击 **“超链接”**）中设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="30223-109">You can also set the value of this cell in the **Hyperlinks** dialog box (in the **Links** group on the **Insert** tab, click **Hyperlink**).</span></span>
  
<span data-ttu-id="30223-110">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 SubAddress 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="30223-110">To get a reference to the SubAddress cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="30223-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="30223-111">Cell name:</span></span>  <br/> | <span data-ttu-id="30223-112">超链接。</span><span class="sxs-lookup"><span data-stu-id="30223-112">Hyperlink.</span></span>  <span data-ttu-id="30223-113">*name*  .SubAddress，其中 Hyperlink  *.name*  是行名称</span><span class="sxs-lookup"><span data-stu-id="30223-113">*name*  .SubAddress where Hyperlink  *.name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="30223-114">若要从程序按索引获取对 **SubAddress** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="30223-114">To get a reference to the **SubAddress** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="30223-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="30223-115">Section index:</span></span>  <br/> |<span data-ttu-id="30223-116">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="30223-116">**visSectionHyperlink**</span></span> <br/> |
| <span data-ttu-id="30223-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="30223-117">Row index:</span></span>  <br/> |<span data-ttu-id="30223-118">**visRow1stHyperlink**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="30223-118">**visRow1stHyperlink** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="30223-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="30223-119">Cell index:</span></span>  <br/> |<span data-ttu-id="30223-120">**visHLinkSubAddress**</span><span class="sxs-lookup"><span data-stu-id="30223-120">**visHLinkSubAddress**</span></span> <br/> |
   

