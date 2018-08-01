---
title: IFERROR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 232fa528-2375-90be-8e18-7a064ce1345e
description: 如果它不计算为错误，则返回主表达式，计算的的结果。 否则，返回的备用表达式的计算的结果。
ms.openlocfilehash: 5915d0cb8219ced190c6b53043188c96d2b56b5f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780439"
---
# <a name="iferror-function"></a><span data-ttu-id="3860b-104">IFERROR 函数</span><span class="sxs-lookup"><span data-stu-id="3860b-104">IFERROR Function</span></span>

<span data-ttu-id="3860b-105">如果它不计算为错误，则返回主表达式，计算的的结果。</span><span class="sxs-lookup"><span data-stu-id="3860b-105">Returns the evaluated result of a primary expression, if it does not evaluate to an error.</span></span> <span data-ttu-id="3860b-106">否则，返回的备用表达式的计算的结果。</span><span class="sxs-lookup"><span data-stu-id="3860b-106">Otherwise, returns the evaluated result of an alternate expression.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="3860b-107">版本信息</span><span class="sxs-lookup"><span data-stu-id="3860b-107">Version Information</span></span>

<span data-ttu-id="3860b-108">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="3860b-108">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="3860b-109">语法</span><span class="sxs-lookup"><span data-stu-id="3860b-109">Syntax</span></span>

<span data-ttu-id="3860b-110">IFERROR (* **主表达式** *，* **备用表达式** *)</span><span class="sxs-lookup"><span data-stu-id="3860b-110">IFERROR(** *primary expression* **, ** *alternate expression* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="3860b-111">参数</span><span class="sxs-lookup"><span data-stu-id="3860b-111">Parameters</span></span>

|<span data-ttu-id="3860b-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="3860b-112">**Name**</span></span>|<span data-ttu-id="3860b-113">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="3860b-113">**Required/Optional**</span></span>|<span data-ttu-id="3860b-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3860b-114">**Data Type**</span></span>|<span data-ttu-id="3860b-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="3860b-115">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3860b-116">_主表达式_</span><span class="sxs-lookup"><span data-stu-id="3860b-116">_primary expression_</span></span> <br/> |<span data-ttu-id="3860b-117">必需</span><span class="sxs-lookup"><span data-stu-id="3860b-117">Required</span></span>  <br/> |<span data-ttu-id="3860b-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="3860b-118">**String**</span></span> <br/> |<span data-ttu-id="3860b-119">要计算的第一个表达式。</span><span class="sxs-lookup"><span data-stu-id="3860b-119">The first expression to evaluate.</span></span>  <br/> |
| <span data-ttu-id="3860b-120">_备用表达式_</span><span class="sxs-lookup"><span data-stu-id="3860b-120">_alternate expression_</span></span> <br/> |<span data-ttu-id="3860b-121">必需</span><span class="sxs-lookup"><span data-stu-id="3860b-121">Required</span></span>  <br/> |<span data-ttu-id="3860b-122">**字符串**</span><span class="sxs-lookup"><span data-stu-id="3860b-122">**String**</span></span> <br/> |<span data-ttu-id="3860b-123">基本表达式计算错误时用于计算的备用表达式。</span><span class="sxs-lookup"><span data-stu-id="3860b-123">The alternate expression to evaluate if the primary expression evaluates to an error.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="3860b-124">返回值</span><span class="sxs-lookup"><span data-stu-id="3860b-124">Return value</span></span>

<span data-ttu-id="3860b-125">因情况而异</span><span class="sxs-lookup"><span data-stu-id="3860b-125">Varies</span></span>
  

