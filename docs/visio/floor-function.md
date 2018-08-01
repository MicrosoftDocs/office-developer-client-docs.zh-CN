---
title: FLOOR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251423
localization_priority: Normal
ms.assetid: 6788bc96-cc86-5f21-781f-67274e7f605a
description: 将数值向 0（零）舍入为下一个整数或 multiple 的下一个实例。
ms.openlocfilehash: f66b993e3ab48fd1abc685b7db5889d5bf24fbfc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780266"
---
# <a name="floor-function"></a><span data-ttu-id="cb881-103">FLOOR 函数</span><span class="sxs-lookup"><span data-stu-id="cb881-103">FLOOR Function</span></span>

<span data-ttu-id="cb881-104">舍入沿靠近 0 （零） 到下一个整数，或_多个_的下一个实例。</span><span class="sxs-lookup"><span data-stu-id="cb881-104">Rounds a number toward 0 (zero), to the next integer, or to the next instance of  _multiple_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="cb881-105">语法</span><span class="sxs-lookup"><span data-stu-id="cb881-105">Syntax</span></span>

<span data-ttu-id="cb881-106">FLOOR (* **数量** *，* **多个** *)</span><span class="sxs-lookup"><span data-stu-id="cb881-106">FLOOR(** *number* **, ** *multiple* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="cb881-107">参数</span><span class="sxs-lookup"><span data-stu-id="cb881-107">Parameters</span></span>

|<span data-ttu-id="cb881-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="cb881-108">**Name**</span></span>|<span data-ttu-id="cb881-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="cb881-109">**Required/Optional**</span></span>|<span data-ttu-id="cb881-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cb881-110">**Data Type**</span></span>|<span data-ttu-id="cb881-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="cb881-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="cb881-112">_number_</span><span class="sxs-lookup"><span data-stu-id="cb881-112">_number_</span></span> <br/> |<span data-ttu-id="cb881-113">必需</span><span class="sxs-lookup"><span data-stu-id="cb881-113">Required</span></span>  <br/> |<span data-ttu-id="cb881-114">**编号**</span><span class="sxs-lookup"><span data-stu-id="cb881-114">**Number**</span></span> <br/> |<span data-ttu-id="cb881-115">要舍入的数值。</span><span class="sxs-lookup"><span data-stu-id="cb881-115">The number to round.</span></span>  <br/> |
| <span data-ttu-id="cb881-116">_多个_</span><span class="sxs-lookup"><span data-stu-id="cb881-116">_multiple_</span></span> <br/> |<span data-ttu-id="cb881-117">必需</span><span class="sxs-lookup"><span data-stu-id="cb881-117">Required</span></span>  <br/> |<span data-ttu-id="cb881-118">**编号**</span><span class="sxs-lookup"><span data-stu-id="cb881-118">**Number**</span></span> <br/> |<span data-ttu-id="cb881-119">要舍入到的倍数。</span><span class="sxs-lookup"><span data-stu-id="cb881-119">The multiple to which to round.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="cb881-120">返回值</span><span class="sxs-lookup"><span data-stu-id="cb881-120">Return value</span></span>

<span data-ttu-id="cb881-121">Number</span><span class="sxs-lookup"><span data-stu-id="cb881-121">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="cb881-122">说明</span><span class="sxs-lookup"><span data-stu-id="cb881-122">Remarks</span></span>

<span data-ttu-id="cb881-123">如果未指定_multiple_ ，则数字将沿靠近 0 到下一个整数舍入。</span><span class="sxs-lookup"><span data-stu-id="cb881-123">If  _multiple_ is not specified, the number rounds toward 0 to the next integer.</span></span> 
  
 <span data-ttu-id="cb881-124">_号码_和_多个_必须具有相同的迹象或 #NUM ！</span><span class="sxs-lookup"><span data-stu-id="cb881-124">_Number_ and  _multiple_ must have the same signs, or a #NUM!</span></span> <span data-ttu-id="cb881-125">将返回错误。</span><span class="sxs-lookup"><span data-stu-id="cb881-125">error is returned.</span></span> <span data-ttu-id="cb881-126">如果_号码_或_多个_不能转换为一个值，#VALUE ！</span><span class="sxs-lookup"><span data-stu-id="cb881-126">If either  _number_ or  _multiple_ cannot be converted to a value, a #VALUE!</span></span> <span data-ttu-id="cb881-127">将返回错误。</span><span class="sxs-lookup"><span data-stu-id="cb881-127">error is returned.</span></span> <span data-ttu-id="cb881-128">如果_号码_或_多个_为 0，则结果为 0。</span><span class="sxs-lookup"><span data-stu-id="cb881-128">If either  _number_ or  _multiple_ is 0, the result is 0.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="cb881-129">示例 1</span><span class="sxs-lookup"><span data-stu-id="cb881-129">Example 1</span></span>

<span data-ttu-id="cb881-130">FLOOR(3.7)</span><span class="sxs-lookup"><span data-stu-id="cb881-130">FLOOR(3.7)</span></span>
  
<span data-ttu-id="cb881-131">返回 3。</span><span class="sxs-lookup"><span data-stu-id="cb881-131">Returns 3.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="cb881-132">示例 2</span><span class="sxs-lookup"><span data-stu-id="cb881-132">Example 2</span></span>

<span data-ttu-id="cb881-133">FLOOR(-3.7)</span><span class="sxs-lookup"><span data-stu-id="cb881-133">FLOOR(-3.7)</span></span>
  
<span data-ttu-id="cb881-134">返回 -3。</span><span class="sxs-lookup"><span data-stu-id="cb881-134">Returns -3.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="cb881-135">示例 3</span><span class="sxs-lookup"><span data-stu-id="cb881-135">Example 3</span></span>

<span data-ttu-id="cb881-136">FLOOR(3.7, 0.5)</span><span class="sxs-lookup"><span data-stu-id="cb881-136">FLOOR(3.7, 0.5)</span></span>
  
<span data-ttu-id="cb881-137">返回 3.5。</span><span class="sxs-lookup"><span data-stu-id="cb881-137">Returns 3.5.</span></span>
  

