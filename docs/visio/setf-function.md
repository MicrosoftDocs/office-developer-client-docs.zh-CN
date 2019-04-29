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
ms.openlocfilehash: 63050de92394ebbdce6cfe053e15347ca3ce5c7f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425972"
---
# <a name="setf-function"></a><span data-ttu-id="d05eb-103">SETF 函数</span><span class="sxs-lookup"><span data-stu-id="d05eb-103">SETF Function</span></span>

<span data-ttu-id="d05eb-104">设置单元格的公式。</span><span class="sxs-lookup"><span data-stu-id="d05eb-104">Sets a cell's formula.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d05eb-105">语法</span><span class="sxs-lookup"><span data-stu-id="d05eb-105">Syntax</span></span>

<span data-ttu-id="d05eb-106">SETF (GETREF (\* \* *cell* \* \*), \* \* *formula* \* \*)</span><span class="sxs-lookup"><span data-stu-id="d05eb-106">SETF( GETREF(\*\* *cell* \*\* ), \*\* *formula* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d05eb-107">参数</span><span class="sxs-lookup"><span data-stu-id="d05eb-107">Parameters</span></span>

|<span data-ttu-id="d05eb-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="d05eb-108">**Name**</span></span>|<span data-ttu-id="d05eb-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d05eb-109">**Required/Optional**</span></span>|<span data-ttu-id="d05eb-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d05eb-110">**Data Type**</span></span>|<span data-ttu-id="d05eb-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d05eb-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d05eb-112">_单元_</span><span class="sxs-lookup"><span data-stu-id="d05eb-112">_cell_</span></span> <br/> |<span data-ttu-id="d05eb-113">必需</span><span class="sxs-lookup"><span data-stu-id="d05eb-113">Required</span></span>  <br/> |<span data-ttu-id="d05eb-114">**String**</span><span class="sxs-lookup"><span data-stu-id="d05eb-114">**String**</span></span> <br/> |<span data-ttu-id="d05eb-115">要设置其公式的单元格。</span><span class="sxs-lookup"><span data-stu-id="d05eb-115">The cell whose formula to set.</span></span>  <br/> |
| <span data-ttu-id="d05eb-116">_formula_</span><span class="sxs-lookup"><span data-stu-id="d05eb-116">_formula_</span></span> <br/> |<span data-ttu-id="d05eb-117">必需</span><span class="sxs-lookup"><span data-stu-id="d05eb-117">Required</span></span>  <br/> |<span data-ttu-id="d05eb-118">**String**</span><span class="sxs-lookup"><span data-stu-id="d05eb-118">**String**</span></span> <br/> |<span data-ttu-id="d05eb-119">要使用的公式。</span><span class="sxs-lookup"><span data-stu-id="d05eb-119">The formula to use.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d05eb-120">说明</span><span class="sxs-lookup"><span data-stu-id="d05eb-120">Remarks</span></span>

<span data-ttu-id="d05eb-121">当计算时, _formula_中表达式的结果将成为_单元格中_的新公式。</span><span class="sxs-lookup"><span data-stu-id="d05eb-121">When evaluated, the result of the expression in  _formula_ becomes the new formula in  _cell_.</span></span> <span data-ttu-id="d05eb-122">如果将_formula_括在引号中, 则会将引用的表达式写入_单元格_。</span><span class="sxs-lookup"><span data-stu-id="d05eb-122">If  _formula_ is enclosed in quotation marks, the quoted expression is written to  _cell_.</span></span> <span data-ttu-id="d05eb-123">若要将_单元格_设置为字符串, 请将_公式_括在三个引号中。</span><span class="sxs-lookup"><span data-stu-id="d05eb-123">To set  _cell_ to a string, enclose  _formula_ in three sets of quotation marks.</span></span> 
  
<span data-ttu-id="d05eb-p102">目标单元格必须使用 GETREF() 引用来指定或必须指定为一个字符串，以避免循环。最好使用 GETREF，因为 Microsoft Visio 能够在形状移到不同的文档时调整引用。</span><span class="sxs-lookup"><span data-stu-id="d05eb-p102">The target cell must be specified using a GETREF() reference or as a string to avoid circularity. Using GETREF is preferred, because Microsoft Visio can adjust references when the shape is moved to a different document.</span></span>
  
<span data-ttu-id="d05eb-126">如果_单元格_不是使用 GETREF 或字符串指定的, 则函数将返回错误, 并且不会更改单元格的公式。</span><span class="sxs-lookup"><span data-stu-id="d05eb-126">If  _cell_ is not specified using GETREF or as a string, the function returns an error, and no cell's formula is changed.</span></span> <span data-ttu-id="d05eb-127">如果_公式_中包含语法错误, 函数将返回错误, 并且_单元格中_的公式不会更改。</span><span class="sxs-lookup"><span data-stu-id="d05eb-127">If  _formula_ contains a syntax error, the function returns an error, and the formula in  _cell_ is not changed.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="d05eb-128">示例 1</span><span class="sxs-lookup"><span data-stu-id="d05eb-128">Example 1</span></span>

<span data-ttu-id="d05eb-129">SETF (GETREF (1.5), 6 + 1 英尺\*中的</span><span class="sxs-lookup"><span data-stu-id="d05eb-129">SETF( GETREF(Scratch.A1), 1.5 in \* 6 + 1 ft)</span></span>
  
<span data-ttu-id="d05eb-130">将 Scratch.A1 的公式设置为 21 英寸。</span><span class="sxs-lookup"><span data-stu-id="d05eb-130">Sets the formula of Scratch.A1 to 21 inches.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="d05eb-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="d05eb-131">Example 2</span></span>

<span data-ttu-id="d05eb-132">SETF (GETREF (), "1.5 \* 6 英尺1英尺")</span><span class="sxs-lookup"><span data-stu-id="d05eb-132">SETF( GETREF(Scratch.A1), "1.5 in \* 6 + 1 ft")</span></span>
  
<span data-ttu-id="d05eb-133">将 Scratch.</span><span class="sxs-lookup"><span data-stu-id="d05eb-133">Sets the formula of Scratch.</span></span> <span data-ttu-id="d05eb-134">A1 到\*6 + 1 英尺的表达式1.5。</span><span class="sxs-lookup"><span data-stu-id="d05eb-134">A1 to the expression 1.5 in\*6+1 ft.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="d05eb-135">示例 3</span><span class="sxs-lookup"><span data-stu-id="d05eb-135">Example 3</span></span>

<span data-ttu-id="d05eb-136">SETF( GETREF(Scratch.A1), """Say """"ahh""""""")</span><span class="sxs-lookup"><span data-stu-id="d05eb-136">SETF( GETREF(Scratch.A1), """Say """"ahh""""""")</span></span>
  
<span data-ttu-id="d05eb-137">将 Scratch.A1 的公式设置为字符串“Say ""ahh""”，该字符串相当于“Say "ahh"”。</span><span class="sxs-lookup"><span data-stu-id="d05eb-137">Sets the formula of Scratch.A1 to the string "Say ""ahh""" which evaluates to Say "ahh".</span></span>
  

