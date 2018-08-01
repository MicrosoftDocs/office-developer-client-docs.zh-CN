---
title: EVALTEXT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251422
localization_priority: Normal
ms.assetid: c9b5b96c-d8c8-6119-e3f1-a2ce9d7c043e
description: 评估 shapename 中文就像它已公式并返回结果。
ms.openlocfilehash: 69e79a23faa9d09aa2ad51f83363064b54742152
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780196"
---
# <a name="evaltext-function"></a><span data-ttu-id="2478e-103">EVALTEXT 函数</span><span class="sxs-lookup"><span data-stu-id="2478e-103">EVALTEXT Function</span></span>

<span data-ttu-id="2478e-104">评估_shapename_中文就像它已公式并返回结果。</span><span class="sxs-lookup"><span data-stu-id="2478e-104">Evaluates the text in  _shapename_ as if it were a formula and returns the result.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="2478e-105">语法</span><span class="sxs-lookup"><span data-stu-id="2478e-105">Syntax</span></span>

<span data-ttu-id="2478e-106">EVALTEXT (* * *shapename ！ theText* * *)</span><span class="sxs-lookup"><span data-stu-id="2478e-106">EVALTEXT(** *shapename!theText* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="2478e-107">参数</span><span class="sxs-lookup"><span data-stu-id="2478e-107">Parameters</span></span>

|<span data-ttu-id="2478e-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="2478e-108">**Name**</span></span>|<span data-ttu-id="2478e-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="2478e-109">**Required/Optional**</span></span>|<span data-ttu-id="2478e-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2478e-110">**Data Type**</span></span>|<span data-ttu-id="2478e-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="2478e-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2478e-112">_shapename ！ theText_</span><span class="sxs-lookup"><span data-stu-id="2478e-112">_shapename!theText_</span></span> <br/> |<span data-ttu-id="2478e-113">必需</span><span class="sxs-lookup"><span data-stu-id="2478e-113">Required</span></span>  <br/> |<span data-ttu-id="2478e-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="2478e-114">**String**</span></span> <br/> |<span data-ttu-id="2478e-115">当关联形状的文本构成改变时触发的单元格。</span><span class="sxs-lookup"><span data-stu-id="2478e-115">A cell that is triggered when the associated shape's text composition changes.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="2478e-116">返回值</span><span class="sxs-lookup"><span data-stu-id="2478e-116">Return value</span></span>

<span data-ttu-id="2478e-117">字符串</span><span class="sxs-lookup"><span data-stu-id="2478e-117">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2478e-118">说明</span><span class="sxs-lookup"><span data-stu-id="2478e-118">Remarks</span></span>

 <span data-ttu-id="2478e-119">_shapename_ 可用来指代某形状（不是当前形状）的文本。</span><span class="sxs-lookup"><span data-stu-id="2478e-119">_shapename_ can be used to refer to the text of a shape other than the current shape.</span></span> 
  
<span data-ttu-id="2478e-p101">如果没有文本，则结果为零。如果无法对文本求值，则该函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="2478e-p101">If there is no text, the result is zero. If the text cannot be evaluated, the function returns an error.</span></span>
  
## <a name="example"></a><span data-ttu-id="2478e-122">示例</span><span class="sxs-lookup"><span data-stu-id="2478e-122">Example</span></span>

<span data-ttu-id="2478e-123">EVALTEXT(Line.2!theText)</span><span class="sxs-lookup"><span data-stu-id="2478e-123">EVALTEXT(Line.2!theText)</span></span> 
  
<span data-ttu-id="2478e-p102">对形状 Line.2 中包含的文本求值。例如，如果 Line.2 包含“4 ft + 0.5 ft”，则返回的值为 4.5 ft。</span><span class="sxs-lookup"><span data-stu-id="2478e-p102">Evaluates the text contained in the shape Line.2. For example, if Line.2 contains "4 ft + 0.5 ft", returns the value 4.5 ft.</span></span> 
  

