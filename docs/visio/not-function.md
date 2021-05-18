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
description: 如果 logicalexpression (FALSE，) 1，则返回 TRUE。 否则，返回 FALSE (0) 。
ms.openlocfilehash: 3359e21654bcc318caf31405093f851eca064119
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413330"
---
# <a name="not-function"></a><span data-ttu-id="bf187-104">NOT 函数</span><span class="sxs-lookup"><span data-stu-id="bf187-104">NOT Function</span></span>

<span data-ttu-id="bf187-105">如果  _logicalexpression_ (FALSE，) 1，则返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="bf187-105">Returns TRUE (1) if  _logicalexpression_ is FALSE.</span></span> <span data-ttu-id="bf187-106">否则，返回 FALSE (0) 。</span><span class="sxs-lookup"><span data-stu-id="bf187-106">Otherwise, it returns FALSE (0).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="bf187-107">语法</span><span class="sxs-lookup"><span data-stu-id="bf187-107">Syntax</span></span>

<span data-ttu-id="bf187-108">NOT (\*\* *logicalexpression* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="bf187-108">NOT(\*\* *logicalexpression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="bf187-109">参数</span><span class="sxs-lookup"><span data-stu-id="bf187-109">Parameters</span></span>

|<span data-ttu-id="bf187-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="bf187-110">**Name**</span></span>|<span data-ttu-id="bf187-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="bf187-111">**Required/Optional**</span></span>|<span data-ttu-id="bf187-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="bf187-112">**Data Type**</span></span>|<span data-ttu-id="bf187-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf187-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="bf187-114">_logicalexpression_</span><span class="sxs-lookup"><span data-stu-id="bf187-114">_logicalexpression_</span></span> <br/> |<span data-ttu-id="bf187-115">必需</span><span class="sxs-lookup"><span data-stu-id="bf187-115">Required</span></span>  <br/> |<span data-ttu-id="bf187-116">**String**</span><span class="sxs-lookup"><span data-stu-id="bf187-116">**String**</span></span> <br/> |<span data-ttu-id="bf187-117">要计算的逻辑表达式。</span><span class="sxs-lookup"><span data-stu-id="bf187-117">The logical expression to evaluate.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="bf187-118">返回值</span><span class="sxs-lookup"><span data-stu-id="bf187-118">Return value</span></span>

<span data-ttu-id="bf187-119">布尔值</span><span class="sxs-lookup"><span data-stu-id="bf187-119">Boolean</span></span>
  
## <a name="example"></a><span data-ttu-id="bf187-120">示例</span><span class="sxs-lookup"><span data-stu-id="bf187-120">Example</span></span>

<span data-ttu-id="bf187-121">不能 (高度 \> 0.75) </span><span class="sxs-lookup"><span data-stu-id="bf187-121">NOT(Height \> 0.75 in)</span></span> 
  
<span data-ttu-id="bf187-p103">如果高度小于或等于 0.75 英寸，则返回 1。如果高度大于 0.75 英寸，则返回 0。</span><span class="sxs-lookup"><span data-stu-id="bf187-p103">Returns 1 if Height is less than or equal to 0.75 inches. Returns 0 if Height is greater than 0.75 inches.</span></span> 
  

