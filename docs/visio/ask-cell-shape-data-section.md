---
title: Ask 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60
localization_priority: Normal
ms.assetid: b499a5eb-db8f-ebd0-d505-c9a002205e7d
description: 确定在创建实例或者重复或复制形状时，是否询问用户以输入该形状的形状数据。
ms.openlocfilehash: 0aa270ff918866d8f683a6408ccd71b6a22d555d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426862"
---
# <a name="ask-cell-shape-data-section"></a><span data-ttu-id="21517-103">Ask 单元格（“Shape Data”内容）</span><span class="sxs-lookup"><span data-stu-id="21517-103">Ask Cell (Shape Data Section)</span></span>

<span data-ttu-id="21517-104">确定在创建实例或者重复或复制形状时，是否询问用户以输入该形状的形状数据。</span><span class="sxs-lookup"><span data-stu-id="21517-104">Determines whether a user is queried to enter shape data for a shape when an instance is created or the shape is duplicated or copied.</span></span>
  
|<span data-ttu-id="21517-105">**值**</span><span class="sxs-lookup"><span data-stu-id="21517-105">**Value**</span></span>|<span data-ttu-id="21517-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="21517-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="21517-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="21517-107">TRUE</span></span>  <br/> |<span data-ttu-id="21517-108">要求用户要在 **“定义形状数据”** 对话框中输入形状数据。</span><span class="sxs-lookup"><span data-stu-id="21517-108">Ask user to enter shape data in the **Define Shape Data** dialog box.</span></span>  <br/> |
|<span data-ttu-id="21517-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="21517-109">FALSE</span></span>  <br/> |<span data-ttu-id="21517-110">不询问用户输入数据。</span><span class="sxs-lookup"><span data-stu-id="21517-110">Do not ask user to enter data.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="21517-111">备注</span><span class="sxs-lookup"><span data-stu-id="21517-111">Remarks</span></span>

<span data-ttu-id="21517-112">此单元格中的值对应于 **“定义形状数据”** 对话框（右键单击形状，指向 **“数据”**，然后单击 **“定义形状数据”**）中的 **“放置时询问”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="21517-112">The value in this cell corresponds to the **Ask on drop** check box in the **Define Shape Data** dialog box (right-click the shape, point to **Data**, and then click **Define Shape Data**).</span></span>
  
<span data-ttu-id="21517-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Ask 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="21517-113">To get a reference to the Ask cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="21517-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="21517-114">Cell name:</span></span>  <br/> |<span data-ttu-id="21517-115">Prop. *name*  .验证 Prop 在何处。  *name*  是自定义属性行的名称。</span><span class="sxs-lookup"><span data-stu-id="21517-115">Prop. *name*  .Verify            where Prop.  *name*  is the name of the custom property row.</span></span>  <br/> |
   
<span data-ttu-id="21517-116">若要从某个程序按索引获取对 Ask 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="21517-116">To get a reference to the Ask cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="21517-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="21517-117">Section index:</span></span>  <br/> |<span data-ttu-id="21517-118">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="21517-118">**visSectionProp**</span></span> <br/> |
|<span data-ttu-id="21517-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="21517-119">Row index:</span></span>  <br/> |<span data-ttu-id="21517-120">**visRowProp**  +  *i* 其中 *i* = 0、1、2,...</span><span class="sxs-lookup"><span data-stu-id="21517-120">**visRowProp** +  *i*            where  *i*  = 0, 1, 2,...</span></span>  <br/> |
|<span data-ttu-id="21517-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="21517-121">Cell index:</span></span>  <br/> |<span data-ttu-id="21517-122">**visCustPropsAsk**</span><span class="sxs-lookup"><span data-stu-id="21517-122">**visCustPropsAsk**</span></span> <br/> |
   

