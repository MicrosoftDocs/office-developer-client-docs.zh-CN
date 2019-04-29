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
description: 将数字向上舍入到下一个整数。
ms.openlocfilehash: 405345ae1d22d599df85e2a640445c8c681ec2f6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416137"
---
# <a name="intup-function"></a><span data-ttu-id="8cb1d-103">INTUP 函数</span><span class="sxs-lookup"><span data-stu-id="8cb1d-103">INTUP Function</span></span>

<span data-ttu-id="8cb1d-104">将数字向上舍入到下一个整数。</span><span class="sxs-lookup"><span data-stu-id="8cb1d-104">Rounds a number up to the next integer.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8cb1d-105">语法</span><span class="sxs-lookup"><span data-stu-id="8cb1d-105">Syntax</span></span>

<span data-ttu-id="8cb1d-106">INTUP (\* **数字** \*)</span><span class="sxs-lookup"><span data-stu-id="8cb1d-106">INTUP(\*\* *number* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="8cb1d-107">参数</span><span class="sxs-lookup"><span data-stu-id="8cb1d-107">Parameters</span></span>

|<span data-ttu-id="8cb1d-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="8cb1d-108">**Name**</span></span>|<span data-ttu-id="8cb1d-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="8cb1d-109">**Required/Optional**</span></span>|<span data-ttu-id="8cb1d-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8cb1d-110">**Data Type**</span></span>|<span data-ttu-id="8cb1d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="8cb1d-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8cb1d-112">_number_</span><span class="sxs-lookup"><span data-stu-id="8cb1d-112">_number_</span></span> <br/> |<span data-ttu-id="8cb1d-113">必需</span><span class="sxs-lookup"><span data-stu-id="8cb1d-113">Required</span></span>  <br/> |<span data-ttu-id="8cb1d-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="8cb1d-114">**Number**</span></span> <br/> |<span data-ttu-id="8cb1d-115">要向上舍入的数。</span><span class="sxs-lookup"><span data-stu-id="8cb1d-115">The number to round up.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="8cb1d-116">示例 1</span><span class="sxs-lookup"><span data-stu-id="8cb1d-116">Example 1</span></span>

<span data-ttu-id="8cb1d-117">INTUP (3.2)</span><span class="sxs-lookup"><span data-stu-id="8cb1d-117">INTUP(3.2)</span></span>
  
<span data-ttu-id="8cb1d-118">返回 4。</span><span class="sxs-lookup"><span data-stu-id="8cb1d-118">Returns 4.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="8cb1d-119">示例 2</span><span class="sxs-lookup"><span data-stu-id="8cb1d-119">Example 2</span></span>

<span data-ttu-id="8cb1d-120">INTUP (-3.2)</span><span class="sxs-lookup"><span data-stu-id="8cb1d-120">INTUP(-3.2)</span></span>
  
<span data-ttu-id="8cb1d-121">返回 -3。</span><span class="sxs-lookup"><span data-stu-id="8cb1d-121">Returns -3.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="8cb1d-122">示例 3</span><span class="sxs-lookup"><span data-stu-id="8cb1d-122">Example 3</span></span>

<span data-ttu-id="8cb1d-123">INTUP (3)</span><span class="sxs-lookup"><span data-stu-id="8cb1d-123">INTUP(3)</span></span>
  
<span data-ttu-id="8cb1d-124">返回 3。</span><span class="sxs-lookup"><span data-stu-id="8cb1d-124">Returns 3.</span></span>
  

