---
title: IFERROR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 232fa528-2375-90be-8e18-7a064ce1345e
description: 返回主表达式的计算结果 (如果未计算出错误)。 否则返回备用表达式的计算结果。
ms.openlocfilehash: 7b9b42b5c7e7053bae862ddadf17e65015d8ecc3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344812"
---
# <a name="iferror-function"></a><span data-ttu-id="df197-104">IFERROR 函数</span><span class="sxs-lookup"><span data-stu-id="df197-104">IFERROR Function</span></span>

<span data-ttu-id="df197-105">返回主表达式的计算结果 (如果未计算出错误)。</span><span class="sxs-lookup"><span data-stu-id="df197-105">Returns the evaluated result of a primary expression, if it does not evaluate to an error.</span></span> <span data-ttu-id="df197-106">否则返回备用表达式的计算结果。</span><span class="sxs-lookup"><span data-stu-id="df197-106">Otherwise, returns the evaluated result of an alternate expression.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="df197-107">版本信息</span><span class="sxs-lookup"><span data-stu-id="df197-107">Version Information</span></span>

<span data-ttu-id="df197-108">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="df197-108">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="df197-109">语法</span><span class="sxs-lookup"><span data-stu-id="df197-109">Syntax</span></span>

<span data-ttu-id="df197-110">IFERROR (\* **主表达式** \*, \* **替代表达式** \*)</span><span class="sxs-lookup"><span data-stu-id="df197-110">IFERROR(\*\* *primary expression* \*\*, \*\* *alternate expression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="df197-111">参数</span><span class="sxs-lookup"><span data-stu-id="df197-111">Parameters</span></span>

|<span data-ttu-id="df197-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="df197-112">**Name**</span></span>|<span data-ttu-id="df197-113">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="df197-113">**Required/Optional**</span></span>|<span data-ttu-id="df197-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="df197-114">**Data Type**</span></span>|<span data-ttu-id="df197-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="df197-115">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="df197-116">_主表达式_</span><span class="sxs-lookup"><span data-stu-id="df197-116">_primary expression_</span></span> <br/> |<span data-ttu-id="df197-117">必需</span><span class="sxs-lookup"><span data-stu-id="df197-117">Required</span></span>  <br/> |<span data-ttu-id="df197-118">**String**</span><span class="sxs-lookup"><span data-stu-id="df197-118">**String**</span></span> <br/> |<span data-ttu-id="df197-119">要计算的第一个表达式。</span><span class="sxs-lookup"><span data-stu-id="df197-119">The first expression to evaluate.</span></span>  <br/> |
| <span data-ttu-id="df197-120">_替代表达式_</span><span class="sxs-lookup"><span data-stu-id="df197-120">_alternate expression_</span></span> <br/> |<span data-ttu-id="df197-121">必需</span><span class="sxs-lookup"><span data-stu-id="df197-121">Required</span></span>  <br/> |<span data-ttu-id="df197-122">**String**</span><span class="sxs-lookup"><span data-stu-id="df197-122">**String**</span></span> <br/> |<span data-ttu-id="df197-123">基本表达式计算错误时用于计算的备用表达式。</span><span class="sxs-lookup"><span data-stu-id="df197-123">The alternate expression to evaluate if the primary expression evaluates to an error.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="df197-124">返回值</span><span class="sxs-lookup"><span data-stu-id="df197-124">Return value</span></span>

<span data-ttu-id="df197-125">各不相同</span><span class="sxs-lookup"><span data-stu-id="df197-125">Varies</span></span>
  

