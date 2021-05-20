---
title: IFERROR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 232fa528-2375-90be-8e18-7a064ce1345e
description: 如果主表达式未计算为错误，则返回该表达式的求值结果。 否则返回备用表达式的计算结果。
ms.openlocfilehash: 7b9b42b5c7e7053bae862ddadf17e65015d8ecc3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431174"
---
# <a name="iferror-function"></a><span data-ttu-id="c1524-104">IFERROR 函数</span><span class="sxs-lookup"><span data-stu-id="c1524-104">IFERROR Function</span></span>

<span data-ttu-id="c1524-105">如果主表达式未计算为错误，则返回该表达式的求值结果。</span><span class="sxs-lookup"><span data-stu-id="c1524-105">Returns the evaluated result of a primary expression, if it does not evaluate to an error.</span></span> <span data-ttu-id="c1524-106">否则返回备用表达式的计算结果。</span><span class="sxs-lookup"><span data-stu-id="c1524-106">Otherwise, returns the evaluated result of an alternate expression.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="c1524-107">版本信息</span><span class="sxs-lookup"><span data-stu-id="c1524-107">Version Information</span></span>

<span data-ttu-id="c1524-108">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="c1524-108">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="c1524-109">语法</span><span class="sxs-lookup"><span data-stu-id="c1524-109">Syntax</span></span>

<span data-ttu-id="c1524-110">IFERROR (\*\* *primary expression* \*\*， \*\* *alternate expression* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="c1524-110">IFERROR(\*\* *primary expression* \*\*, \*\* *alternate expression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c1524-111">参数</span><span class="sxs-lookup"><span data-stu-id="c1524-111">Parameters</span></span>

|<span data-ttu-id="c1524-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="c1524-112">**Name**</span></span>|<span data-ttu-id="c1524-113">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c1524-113">**Required/Optional**</span></span>|<span data-ttu-id="c1524-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c1524-114">**Data Type**</span></span>|<span data-ttu-id="c1524-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="c1524-115">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c1524-116">_主表达式_</span><span class="sxs-lookup"><span data-stu-id="c1524-116">_primary expression_</span></span> <br/> |<span data-ttu-id="c1524-117">必需</span><span class="sxs-lookup"><span data-stu-id="c1524-117">Required</span></span>  <br/> |<span data-ttu-id="c1524-118">**String**</span><span class="sxs-lookup"><span data-stu-id="c1524-118">**String**</span></span> <br/> |<span data-ttu-id="c1524-119">要计算的第一个表达式。</span><span class="sxs-lookup"><span data-stu-id="c1524-119">The first expression to evaluate.</span></span>  <br/> |
| <span data-ttu-id="c1524-120">_备用表达式_</span><span class="sxs-lookup"><span data-stu-id="c1524-120">_alternate expression_</span></span> <br/> |<span data-ttu-id="c1524-121">必需</span><span class="sxs-lookup"><span data-stu-id="c1524-121">Required</span></span>  <br/> |<span data-ttu-id="c1524-122">**String**</span><span class="sxs-lookup"><span data-stu-id="c1524-122">**String**</span></span> <br/> |<span data-ttu-id="c1524-123">基本表达式计算错误时用于计算的备用表达式。</span><span class="sxs-lookup"><span data-stu-id="c1524-123">The alternate expression to evaluate if the primary expression evaluates to an error.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="c1524-124">返回值</span><span class="sxs-lookup"><span data-stu-id="c1524-124">Return value</span></span>

<span data-ttu-id="c1524-125">各不相同</span><span class="sxs-lookup"><span data-stu-id="c1524-125">Varies</span></span>
  

