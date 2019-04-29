---
title: NoCoauth 单元格 ("Document Properties" 内容)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f2095c9-ce09-48f7-b160-c9822d96a96c
description: 设置在合著会话中, 多个作者是否可以同时编辑存储在 microsoft SharePoint 2013 服务器或 microsoft OneDrive 上的文档。
ms.openlocfilehash: a76e2d3b2c3cf6e99e37596b016f448b0be56fd3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420512"
---
# <a name="nocoauth-cell-document-properties-section"></a><span data-ttu-id="3a234-103">NoCoauth 单元格 ("Document Properties" 内容)</span><span class="sxs-lookup"><span data-stu-id="3a234-103">NoCoauth Cell (Document Properties Section)</span></span>

<span data-ttu-id="3a234-104">设置在合著会话中, 多个作者是否可以同时编辑存储在 microsoft SharePoint 2013 服务器或 microsoft OneDrive 上的文档。</span><span class="sxs-lookup"><span data-stu-id="3a234-104">Sets whether a document stored on a Microsoft SharePoint 2013 server or Microsoft OneDrive can be edited by multiple authors simultaneously in a coauthoring session.</span></span>
  
|<span data-ttu-id="3a234-105">**值**</span><span class="sxs-lookup"><span data-stu-id="3a234-105">**Value**</span></span>|<span data-ttu-id="3a234-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="3a234-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3a234-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="3a234-107">TRUE</span></span>  <br/> |<span data-ttu-id="3a234-108">文档不能为合著, 在打开时已被锁定, 无法编辑。</span><span class="sxs-lookup"><span data-stu-id="3a234-108">The document cannot be coauthored and is locked for editing when open.</span></span>  <br/> |
|<span data-ttu-id="3a234-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="3a234-109">FALSE</span></span>  <br/> |<span data-ttu-id="3a234-110">该文档可以是合著。</span><span class="sxs-lookup"><span data-stu-id="3a234-110">The document can be coauthored.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3a234-111">说明</span><span class="sxs-lookup"><span data-stu-id="3a234-111">Remarks</span></span>

<span data-ttu-id="3a234-112">若要从另一个公式按名称获取对**NoCoauth**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="3a234-112">To get a reference to the **NoCoauth** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3a234-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3a234-113">Cell name:</span></span>  <br/> | <span data-ttu-id="3a234-114">NoCoauth</span><span class="sxs-lookup"><span data-stu-id="3a234-114">NoCoauth</span></span>  <br/> |
   
<span data-ttu-id="3a234-115">若要从某个程序按索引获取对**NoCoauth**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="3a234-115">To get a reference to the **NoCoauth** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3a234-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3a234-116">Section index:</span></span>  <br/> |<span data-ttu-id="3a234-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="3a234-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="3a234-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="3a234-118">Row index:</span></span>  <br/> |<span data-ttu-id="3a234-119">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="3a234-119">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="3a234-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3a234-120">Cell index:</span></span>  <br/> |<span data-ttu-id="3a234-121">**visDocNoCoauth**</span><span class="sxs-lookup"><span data-stu-id="3a234-121">**visDocNoCoauth**</span></span> <br/> |
   

