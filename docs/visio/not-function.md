---
title: NOT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251469
localization_priority: Normal
ms.assetid: 65873b32-2406-7c33-8e68-802461f467b2
description: 如果在 logicalexpression 为 false，则，返回 TRUE (1)。 否则，将返回 FALSE (0)。
ms.openlocfilehash: e2359aaab18469cd4f272f71aca8d899a12b2120
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780796"
---
# <a name="not-function"></a><span data-ttu-id="6dfdb-104">NOT 函数</span><span class="sxs-lookup"><span data-stu-id="6dfdb-104">NOT Function</span></span>

<span data-ttu-id="6dfdb-105">如果_在 logicalexpression_为 false，则，返回 TRUE (1)。</span><span class="sxs-lookup"><span data-stu-id="6dfdb-105">Returns TRUE (1) if  _logicalexpression_ is FALSE.</span></span> <span data-ttu-id="6dfdb-106">否则，将返回 FALSE (0)。</span><span class="sxs-lookup"><span data-stu-id="6dfdb-106">Otherwise, it returns FALSE (0).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="6dfdb-107">语法</span><span class="sxs-lookup"><span data-stu-id="6dfdb-107">Syntax</span></span>

<span data-ttu-id="6dfdb-108">不 (* **在 logicalexpression* * *)</span><span class="sxs-lookup"><span data-stu-id="6dfdb-108">NOT(** *logicalexpression* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="6dfdb-109">参数</span><span class="sxs-lookup"><span data-stu-id="6dfdb-109">Parameters</span></span>

|<span data-ttu-id="6dfdb-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="6dfdb-110">**Name**</span></span>|<span data-ttu-id="6dfdb-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="6dfdb-111">**Required/Optional**</span></span>|<span data-ttu-id="6dfdb-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="6dfdb-112">**Data Type**</span></span>|<span data-ttu-id="6dfdb-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="6dfdb-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="6dfdb-114">_在 logicalexpression_</span><span class="sxs-lookup"><span data-stu-id="6dfdb-114">_logicalexpression_</span></span> <br/> |<span data-ttu-id="6dfdb-115">必需</span><span class="sxs-lookup"><span data-stu-id="6dfdb-115">Required</span></span>  <br/> |<span data-ttu-id="6dfdb-116">**字符串**</span><span class="sxs-lookup"><span data-stu-id="6dfdb-116">**String**</span></span> <br/> |<span data-ttu-id="6dfdb-117">要计算的逻辑表达式。</span><span class="sxs-lookup"><span data-stu-id="6dfdb-117">The logical expression to evaluate.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="6dfdb-118">返回值</span><span class="sxs-lookup"><span data-stu-id="6dfdb-118">Return value</span></span>

<span data-ttu-id="6dfdb-119">Boolean</span><span class="sxs-lookup"><span data-stu-id="6dfdb-119">Boolean</span></span>
  
## <a name="example"></a><span data-ttu-id="6dfdb-120">示例</span><span class="sxs-lookup"><span data-stu-id="6dfdb-120">Example</span></span>

<span data-ttu-id="6dfdb-121">不 (高度\>0.75 中)</span><span class="sxs-lookup"><span data-stu-id="6dfdb-121">NOT(Height \> 0.75 in)</span></span> 
  
<span data-ttu-id="6dfdb-p103">如果高度小于或等于 0.75 英寸，则返回 1。如果高度大于 0.75 英寸，则返回 0。</span><span class="sxs-lookup"><span data-stu-id="6dfdb-p103">Returns 1 if Height is less than or equal to 0.75 inches. Returns 0 if Height is greater than 0.75 inches.</span></span> 
  

