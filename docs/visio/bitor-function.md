---
title: BITOR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251400
localization_priority: Normal
ms.assetid: 1d0954c5-b2cb-6c5d-62b3-a68011cf0c85
description: 返回一个 16 位二进制数，如果二进制数字 1 或二进制数字 2 中的对应位为 1，则其中每个位都设置为 1。 只有在二进制数字 1 和二进制数字 2 中对应的位都为 0 时，该位才设置为 0。
ms.openlocfilehash: 13bda2c6c65557b1f8372432cf919b2aaf2d75de
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408080"
---
# <a name="bitor-function"></a><span data-ttu-id="61c41-104">BITOR 函数</span><span class="sxs-lookup"><span data-stu-id="61c41-104">BITOR Function</span></span>

<span data-ttu-id="61c41-105">返回一个 16 位二进制数，如果二进制  *数字 1*  或二进制数字  *2*  中的对应位为 1，则其中每个位都设置为 1。</span><span class="sxs-lookup"><span data-stu-id="61c41-105">Returns a 16-bit binary number in which each bit is set to 1 if the corresponding bit in either  *binary number1*  or  *binary number2*  is 1.</span></span> <span data-ttu-id="61c41-106">只有在二进制数字 *1* 和二进制数字 2 中对应的位都为 0 时，该位 *才设置为 0。*</span><span class="sxs-lookup"><span data-stu-id="61c41-106">The bit is set to 0 only if the corresponding bit is 0 in both  *binary number1*  and  *binary number2*  .</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="61c41-107">语法</span><span class="sxs-lookup"><span data-stu-id="61c41-107">Syntax</span></span>

<span data-ttu-id="61c41-108">BITOR (\*\* *binary number1* \*\*， \*\* *binary number2* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="61c41-108">BITOR(\*\* *binary number1* \*\*, \*\* *binary number2* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="61c41-109">参数</span><span class="sxs-lookup"><span data-stu-id="61c41-109">Parameters</span></span>

|<span data-ttu-id="61c41-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="61c41-110">**Name**</span></span>|<span data-ttu-id="61c41-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="61c41-111">**Required/Optional**</span></span>|<span data-ttu-id="61c41-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="61c41-112">**Data Type**</span></span>|<span data-ttu-id="61c41-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="61c41-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="61c41-114">_binary number1_</span><span class="sxs-lookup"><span data-stu-id="61c41-114">_binary number1_</span></span> <br/> |<span data-ttu-id="61c41-115">必需</span><span class="sxs-lookup"><span data-stu-id="61c41-115">Required</span></span>  <br/> |<span data-ttu-id="61c41-116">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="61c41-116">**Numeric**</span></span> <br/> |<span data-ttu-id="61c41-117">第一个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="61c41-117">The first 16-bit binary number.</span></span>  <br/> |
| <span data-ttu-id="61c41-118">_binary number2_</span><span class="sxs-lookup"><span data-stu-id="61c41-118">_binary number2_</span></span> <br/> |<span data-ttu-id="61c41-119">必需</span><span class="sxs-lookup"><span data-stu-id="61c41-119">Required</span></span>  <br/> |<span data-ttu-id="61c41-120">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="61c41-120">**Numeric**</span></span> <br/> |<span data-ttu-id="61c41-121">第二个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="61c41-121">The second 16-bit binary number.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="61c41-122">返回值</span><span class="sxs-lookup"><span data-stu-id="61c41-122">Return value</span></span>

<span data-ttu-id="61c41-123">16 位二进制数</span><span class="sxs-lookup"><span data-stu-id="61c41-123">16-bit Binary</span></span>
  
## <a name="example"></a><span data-ttu-id="61c41-124">示例</span><span class="sxs-lookup"><span data-stu-id="61c41-124">Example</span></span>

<span data-ttu-id="61c41-125">BITOR (12，6) </span><span class="sxs-lookup"><span data-stu-id="61c41-125">BITOR(12,6)</span></span>
  
<span data-ttu-id="61c41-p103">返回 14。12 = 0...01100。6 = 0...00110。因此，BITOR(12,6) = 0...01110。</span><span class="sxs-lookup"><span data-stu-id="61c41-p103">Returns 14. The 12 = 0...01100. The 6 = 0...00110. Therefore, BITOR(12,6) = 0...01110.</span></span>
  

