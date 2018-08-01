---
title: SETF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251496
localization_priority: Normal
ms.assetid: fcf415c1-171f-b75f-6e40-2bbdbe8b1cfb
description: 设置单元格的公式。
ms.openlocfilehash: a1e6a12014a77a20c0968b3ed2f7bc25badad8ce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781242"
---
# <a name="setf-function"></a><span data-ttu-id="001a5-103">SETF 函数</span><span class="sxs-lookup"><span data-stu-id="001a5-103">SETF Function</span></span>

<span data-ttu-id="001a5-104">设置单元格的公式。</span><span class="sxs-lookup"><span data-stu-id="001a5-104">Sets a cell's formula.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="001a5-105">语法</span><span class="sxs-lookup"><span data-stu-id="001a5-105">Syntax</span></span>

<span data-ttu-id="001a5-106">SETF (GETREF (* **单元格** *)，* **公式** *)</span><span class="sxs-lookup"><span data-stu-id="001a5-106">SETF( GETREF(** *cell* ** ), ** *formula* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="001a5-107">参数</span><span class="sxs-lookup"><span data-stu-id="001a5-107">Parameters</span></span>

|<span data-ttu-id="001a5-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="001a5-108">**Name**</span></span>|<span data-ttu-id="001a5-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="001a5-109">**Required/Optional**</span></span>|<span data-ttu-id="001a5-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="001a5-110">**Data Type**</span></span>|<span data-ttu-id="001a5-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="001a5-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="001a5-112">_单元格_</span><span class="sxs-lookup"><span data-stu-id="001a5-112">_cell_</span></span> <br/> |<span data-ttu-id="001a5-113">必需</span><span class="sxs-lookup"><span data-stu-id="001a5-113">Required</span></span>  <br/> |<span data-ttu-id="001a5-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="001a5-114">**String**</span></span> <br/> |<span data-ttu-id="001a5-115">单元格要设置其公式。</span><span class="sxs-lookup"><span data-stu-id="001a5-115">The cell whose formula to set.</span></span>  <br/> |
| <span data-ttu-id="001a5-116">_formula_</span><span class="sxs-lookup"><span data-stu-id="001a5-116">_formula_</span></span> <br/> |<span data-ttu-id="001a5-117">必需</span><span class="sxs-lookup"><span data-stu-id="001a5-117">Required</span></span>  <br/> |<span data-ttu-id="001a5-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="001a5-118">**String**</span></span> <br/> |<span data-ttu-id="001a5-119">要使用的公式。</span><span class="sxs-lookup"><span data-stu-id="001a5-119">The formula to use.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="001a5-120">注解</span><span class="sxs-lookup"><span data-stu-id="001a5-120">Remarks</span></span>

<span data-ttu-id="001a5-121">在计算时，在_公式_表达式的结果将成为_单元_格中的新公式。</span><span class="sxs-lookup"><span data-stu-id="001a5-121">When evaluated, the result of the expression in  _formula_ becomes the new formula in  _cell_.</span></span> <span data-ttu-id="001a5-122">如果_公式_括在引号内，则引用的表达式写入_单元格_。</span><span class="sxs-lookup"><span data-stu-id="001a5-122">If  _formula_ is enclosed in quotation marks, the quoted expression is written to  _cell_.</span></span> <span data-ttu-id="001a5-123">将_单元格_设置为一个字符串，将括在引号三组的_公式_。</span><span class="sxs-lookup"><span data-stu-id="001a5-123">To set  _cell_ to a string, enclose  _formula_ in three sets of quotation marks.</span></span> 
  
<span data-ttu-id="001a5-p102">目标单元格必须使用 GETREF() 引用来指定或必须指定为一个字符串，以避免循环。最好使用 GETREF，因为 Microsoft Visio 能够在形状移到不同的文档时调整引用。</span><span class="sxs-lookup"><span data-stu-id="001a5-p102">The target cell must be specified using a GETREF() reference or as a string to avoid circularity. Using GETREF is preferred, because Microsoft Visio can adjust references when the shape is moved to a different document.</span></span>
  
<span data-ttu-id="001a5-126">如果未使用 GETREF 指定_单元格_或为 string，函数将返回错误，并且更改任何单元格的公式。</span><span class="sxs-lookup"><span data-stu-id="001a5-126">If  _cell_ is not specified using GETREF or as a string, the function returns an error, and no cell's formula is changed.</span></span> <span data-ttu-id="001a5-127">如果_公式_包含语法错误，函数将返回错误，并且不更改_单元_格中的公式。</span><span class="sxs-lookup"><span data-stu-id="001a5-127">If  _formula_ contains a syntax error, the function returns an error, and the formula in  _cell_ is not changed.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="001a5-128">示例 1</span><span class="sxs-lookup"><span data-stu-id="001a5-128">Example 1</span></span>

<span data-ttu-id="001a5-129">SETF (GETREF(Scratch.A1)，1.5 中\*6 + 1 ft)</span><span class="sxs-lookup"><span data-stu-id="001a5-129">SETF( GETREF(Scratch.A1), 1.5 in \* 6 + 1 ft)</span></span>
  
<span data-ttu-id="001a5-130">将 Scratch.A1 的公式设置为 21 英寸。</span><span class="sxs-lookup"><span data-stu-id="001a5-130">Sets the formula of Scratch.A1 to 21 inches.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="001a5-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="001a5-131">Example 2</span></span>

<span data-ttu-id="001a5-132">SETF (GETREF(Scratch.A1)，"中的 1.5 \* 6 + 1 ft")</span><span class="sxs-lookup"><span data-stu-id="001a5-132">SETF( GETREF(Scratch.A1), "1.5 in \* 6 + 1 ft")</span></span>
  
<span data-ttu-id="001a5-133">设置挑战的公式。</span><span class="sxs-lookup"><span data-stu-id="001a5-133">Sets the formula of Scratch.</span></span> <span data-ttu-id="001a5-134">对表达式 1.5 中 A1\*6 + 1 英尺。</span><span class="sxs-lookup"><span data-stu-id="001a5-134">A1 to the expression 1.5 in\*6+1 ft.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="001a5-135">示例 3</span><span class="sxs-lookup"><span data-stu-id="001a5-135">Example 3</span></span>

<span data-ttu-id="001a5-136">SETF( GETREF(Scratch.A1), """Say """"ahh""""""")</span><span class="sxs-lookup"><span data-stu-id="001a5-136">SETF( GETREF(Scratch.A1), """Say """"ahh""""""")</span></span>
  
<span data-ttu-id="001a5-137">将 Scratch.A1 的公式设置为字符串“Say ""ahh""”，该字符串相当于“Say "ahh"”。</span><span class="sxs-lookup"><span data-stu-id="001a5-137">Sets the formula of Scratch.A1 to the string "Say ""ahh""" which evaluates to Say "ahh".</span></span>
  

