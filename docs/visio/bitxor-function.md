---
title: BITXOR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251401
localization_priority: Normal
ms.assetid: 672eacaf-a374-c7e2-b39b-8d42d2371aee
description: 返回一个16位二进制数, 在该数字中, 如果二进制数字1和二进制数字2中的相应位不同时为 1, 则将每位设置为1。 否则, 将位设置为0。
ms.openlocfilehash: ab8ff46fe98512d963ef4ecd5c37127353827725
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439231"
---
# <a name="bitxor-function"></a><span data-ttu-id="2e30d-104">BITXOR 函数</span><span class="sxs-lookup"><span data-stu-id="2e30d-104">BITXOR Function</span></span>

<span data-ttu-id="2e30d-105">返回一个16位二进制数, 在该数字中, 如果二进制数字1和二进制数字2中的相应位不同时为 1, 则将每位设置为1。</span><span class="sxs-lookup"><span data-stu-id="2e30d-105">Returns a 16-bit binary number in which each bit is set to 1 if the corresponding bit in either but not both binary number1 and binary number2 is 1.</span></span> <span data-ttu-id="2e30d-106">否则, 将位设置为0。</span><span class="sxs-lookup"><span data-stu-id="2e30d-106">Otherwise, the bit is set to 0.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="2e30d-107">语法</span><span class="sxs-lookup"><span data-stu-id="2e30d-107">Syntax</span></span>

<span data-ttu-id="2e30d-108">BITXOR (\* \* *binary 1* \* \*, \* \**二进制数字 2* \* \*)</span><span class="sxs-lookup"><span data-stu-id="2e30d-108">BITXOR(\*\* *binary number1* \*\*, \*\* *binary number2* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="2e30d-109">参数</span><span class="sxs-lookup"><span data-stu-id="2e30d-109">Parameters</span></span>

|<span data-ttu-id="2e30d-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="2e30d-110">**Name**</span></span>|<span data-ttu-id="2e30d-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="2e30d-111">**Required/Optional**</span></span>|<span data-ttu-id="2e30d-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2e30d-112">**Data Type**</span></span>|<span data-ttu-id="2e30d-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="2e30d-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2e30d-114">_二进制数字1_</span><span class="sxs-lookup"><span data-stu-id="2e30d-114">_binary number1_</span></span> <br/> |<span data-ttu-id="2e30d-115">必需</span><span class="sxs-lookup"><span data-stu-id="2e30d-115">Required</span></span>  <br/> |<span data-ttu-id="2e30d-116">**数值**</span><span class="sxs-lookup"><span data-stu-id="2e30d-116">**Numeric**</span></span> <br/> |<span data-ttu-id="2e30d-117">第一个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="2e30d-117">The first 16-bit binary number.</span></span>  <br/> |
| <span data-ttu-id="2e30d-118">_二进制数字2_</span><span class="sxs-lookup"><span data-stu-id="2e30d-118">_binary number2_</span></span> <br/> |<span data-ttu-id="2e30d-119">必需</span><span class="sxs-lookup"><span data-stu-id="2e30d-119">Required</span></span>  <br/> |<span data-ttu-id="2e30d-120">**数值**</span><span class="sxs-lookup"><span data-stu-id="2e30d-120">**Numeric**</span></span> <br/> |<span data-ttu-id="2e30d-121">第二个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="2e30d-121">The second 16-bit binary number.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="2e30d-122">返回值</span><span class="sxs-lookup"><span data-stu-id="2e30d-122">Return value</span></span>

<span data-ttu-id="2e30d-123">16 位二进制数</span><span class="sxs-lookup"><span data-stu-id="2e30d-123">16-bit Binary</span></span>
  
## <a name="example"></a><span data-ttu-id="2e30d-124">示例</span><span class="sxs-lookup"><span data-stu-id="2e30d-124">Example</span></span>

<span data-ttu-id="2e30d-125">BITXOR (12, 6)</span><span class="sxs-lookup"><span data-stu-id="2e30d-125">BITXOR(12,6)</span></span>
  
<span data-ttu-id="2e30d-p103">返回 10。12 = 0...01100。6 = 0...00110。因此，BITXOR(12,6) = 0...01010。</span><span class="sxs-lookup"><span data-stu-id="2e30d-p103">Returns 10. The 12 = 0...01100. The 6 = 0...00110. Therefore, BITXOR(12,6) = 0...01010.</span></span>
  

