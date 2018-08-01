---
title: INTUP 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251446
localization_priority: Normal
ms.assetid: ce193ce1-c7fd-6609-ad37-a3a28b30a1bd
description: 舍入到下一个整数为止。
ms.openlocfilehash: f54a08fa059d50102a6377b7e368e7e388297acc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780478"
---
# <a name="intup-function"></a><span data-ttu-id="7f8c0-103">INTUP 函数</span><span class="sxs-lookup"><span data-stu-id="7f8c0-103">INTUP Function</span></span>

<span data-ttu-id="7f8c0-104">舍入到下一个整数为止。</span><span class="sxs-lookup"><span data-stu-id="7f8c0-104">Rounds a number up to the next integer.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="7f8c0-105">语法</span><span class="sxs-lookup"><span data-stu-id="7f8c0-105">Syntax</span></span>

<span data-ttu-id="7f8c0-106">INTUP (* **数量** *)</span><span class="sxs-lookup"><span data-stu-id="7f8c0-106">INTUP(** *number* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="7f8c0-107">参数</span><span class="sxs-lookup"><span data-stu-id="7f8c0-107">Parameters</span></span>

|<span data-ttu-id="7f8c0-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="7f8c0-108">**Name**</span></span>|<span data-ttu-id="7f8c0-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="7f8c0-109">**Required/Optional**</span></span>|<span data-ttu-id="7f8c0-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7f8c0-110">**Data Type**</span></span>|<span data-ttu-id="7f8c0-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="7f8c0-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7f8c0-112">_number_</span><span class="sxs-lookup"><span data-stu-id="7f8c0-112">_number_</span></span> <br/> |<span data-ttu-id="7f8c0-113">必需</span><span class="sxs-lookup"><span data-stu-id="7f8c0-113">Required</span></span>  <br/> |<span data-ttu-id="7f8c0-114">**编号**</span><span class="sxs-lookup"><span data-stu-id="7f8c0-114">**Number**</span></span> <br/> |<span data-ttu-id="7f8c0-115">要向上舍入的数。</span><span class="sxs-lookup"><span data-stu-id="7f8c0-115">The number to round up.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="7f8c0-116">示例 1</span><span class="sxs-lookup"><span data-stu-id="7f8c0-116">Example 1</span></span>

<span data-ttu-id="7f8c0-117">INTUP(3.2)</span><span class="sxs-lookup"><span data-stu-id="7f8c0-117">INTUP(3.2)</span></span>
  
<span data-ttu-id="7f8c0-118">返回 4。</span><span class="sxs-lookup"><span data-stu-id="7f8c0-118">Returns 4.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="7f8c0-119">示例 2</span><span class="sxs-lookup"><span data-stu-id="7f8c0-119">Example 2</span></span>

<span data-ttu-id="7f8c0-120">INTUP(-3.2)</span><span class="sxs-lookup"><span data-stu-id="7f8c0-120">INTUP(-3.2)</span></span>
  
<span data-ttu-id="7f8c0-121">返回 -3。</span><span class="sxs-lookup"><span data-stu-id="7f8c0-121">Returns -3.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="7f8c0-122">示例 3</span><span class="sxs-lookup"><span data-stu-id="7f8c0-122">Example 3</span></span>

<span data-ttu-id="7f8c0-123">INTUP(3)</span><span class="sxs-lookup"><span data-stu-id="7f8c0-123">INTUP(3)</span></span>
  
<span data-ttu-id="7f8c0-124">返回 3。</span><span class="sxs-lookup"><span data-stu-id="7f8c0-124">Returns 3.</span></span>
  

