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
description: 如果 logicalexpression 为 FALSE, 则返回 TRUE (1)。 否则, 它将返回 FALSE (0)。
ms.openlocfilehash: 3359e21654bcc318caf31405093f851eca064119
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341136"
---
# <a name="not-function"></a><span data-ttu-id="8f488-104">NOT 函数</span><span class="sxs-lookup"><span data-stu-id="8f488-104">NOT Function</span></span>

<span data-ttu-id="8f488-105">如果_logicalexpression_为 FALSE, 则返回 TRUE (1)。</span><span class="sxs-lookup"><span data-stu-id="8f488-105">Returns TRUE (1) if  _logicalexpression_ is FALSE.</span></span> <span data-ttu-id="8f488-106">否则, 它将返回 FALSE (0)。</span><span class="sxs-lookup"><span data-stu-id="8f488-106">Otherwise, it returns FALSE (0).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="8f488-107">语法</span><span class="sxs-lookup"><span data-stu-id="8f488-107">Syntax</span></span>

<span data-ttu-id="8f488-108">NOT (\* \* *logicalexpression* \* \*)</span><span class="sxs-lookup"><span data-stu-id="8f488-108">NOT(\*\* *logicalexpression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="8f488-109">参数</span><span class="sxs-lookup"><span data-stu-id="8f488-109">Parameters</span></span>

|<span data-ttu-id="8f488-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="8f488-110">**Name**</span></span>|<span data-ttu-id="8f488-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="8f488-111">**Required/Optional**</span></span>|<span data-ttu-id="8f488-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8f488-112">**Data Type**</span></span>|<span data-ttu-id="8f488-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f488-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8f488-114">_logicalexpression_</span><span class="sxs-lookup"><span data-stu-id="8f488-114">_logicalexpression_</span></span> <br/> |<span data-ttu-id="8f488-115">必需</span><span class="sxs-lookup"><span data-stu-id="8f488-115">Required</span></span>  <br/> |<span data-ttu-id="8f488-116">**String**</span><span class="sxs-lookup"><span data-stu-id="8f488-116">**String**</span></span> <br/> |<span data-ttu-id="8f488-117">要计算的逻辑表达式。</span><span class="sxs-lookup"><span data-stu-id="8f488-117">The logical expression to evaluate.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="8f488-118">返回值</span><span class="sxs-lookup"><span data-stu-id="8f488-118">Return value</span></span>

<span data-ttu-id="8f488-119">布尔值</span><span class="sxs-lookup"><span data-stu-id="8f488-119">Boolean</span></span>
  
## <a name="example"></a><span data-ttu-id="8f488-120">示例</span><span class="sxs-lookup"><span data-stu-id="8f488-120">Example</span></span>

<span data-ttu-id="8f488-121">不是 ( \>高度 0.75 in)</span><span class="sxs-lookup"><span data-stu-id="8f488-121">NOT(Height \> 0.75 in)</span></span> 
  
<span data-ttu-id="8f488-122">如果高度小于或等于 0.75 英寸，则返回 1。</span><span class="sxs-lookup"><span data-stu-id="8f488-122">Returns 1 if Height is less than or equal to 0.75 inches.</span></span> <span data-ttu-id="8f488-123">如果高度大于 0.75 英寸，则返回 0。</span><span class="sxs-lookup"><span data-stu-id="8f488-123">Returns 0 if Height is greater than 0.75 inches.</span></span> 
  

