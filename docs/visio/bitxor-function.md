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
description: 返回其中每个位设置为 1 如果二进制 number1 和二进制数字 2 但不是能同时中相应的位为 1 16 位二进制数。 否则，将位设置为 0。
ms.openlocfilehash: a0e03258bcfe694dc3bec5469095eff90fb94f1a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779753"
---
# <a name="bitxor-function"></a><span data-ttu-id="1414a-104">BITXOR 函数</span><span class="sxs-lookup"><span data-stu-id="1414a-104">BITXOR Function</span></span>

<span data-ttu-id="1414a-105">返回其中每个位设置为 1 如果二进制 number1 和二进制数字 2 但不是能同时中相应的位为 1 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="1414a-105">Returns a 16-bit binary number in which each bit is set to 1 if the corresponding bit in either but not both binary number1 and binary number2 is 1.</span></span> <span data-ttu-id="1414a-106">否则，将位设置为 0。</span><span class="sxs-lookup"><span data-stu-id="1414a-106">Otherwise, the bit is set to 0.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="1414a-107">语法</span><span class="sxs-lookup"><span data-stu-id="1414a-107">Syntax</span></span>

<span data-ttu-id="1414a-108">BITXOR (* **二进制数字 1* * *，* **二进制数字 2* * *)</span><span class="sxs-lookup"><span data-stu-id="1414a-108">BITXOR(** *binary number1* **, ** *binary number2* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="1414a-109">参数</span><span class="sxs-lookup"><span data-stu-id="1414a-109">Parameters</span></span>

|<span data-ttu-id="1414a-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="1414a-110">**Name**</span></span>|<span data-ttu-id="1414a-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="1414a-111">**Required/Optional**</span></span>|<span data-ttu-id="1414a-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1414a-112">**Data Type**</span></span>|<span data-ttu-id="1414a-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="1414a-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1414a-114">_二进制 number1_</span><span class="sxs-lookup"><span data-stu-id="1414a-114">_binary number1_</span></span> <br/> |<span data-ttu-id="1414a-115">必需</span><span class="sxs-lookup"><span data-stu-id="1414a-115">Required</span></span>  <br/> |<span data-ttu-id="1414a-116">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="1414a-116">**Numeric**</span></span> <br/> |<span data-ttu-id="1414a-117">第一个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="1414a-117">The first 16-bit binary number.</span></span>  <br/> |
| <span data-ttu-id="1414a-118">_二进制数字 2_</span><span class="sxs-lookup"><span data-stu-id="1414a-118">_binary number2_</span></span> <br/> |<span data-ttu-id="1414a-119">必需</span><span class="sxs-lookup"><span data-stu-id="1414a-119">Required</span></span>  <br/> |<span data-ttu-id="1414a-120">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="1414a-120">**Numeric**</span></span> <br/> |<span data-ttu-id="1414a-121">第二个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="1414a-121">The second 16-bit binary number.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="1414a-122">返回值</span><span class="sxs-lookup"><span data-stu-id="1414a-122">Return value</span></span>

<span data-ttu-id="1414a-123">16 位二进制数</span><span class="sxs-lookup"><span data-stu-id="1414a-123">16-bit Binary</span></span>
  
## <a name="example"></a><span data-ttu-id="1414a-124">示例</span><span class="sxs-lookup"><span data-stu-id="1414a-124">Example</span></span>

<span data-ttu-id="1414a-125">BITXOR(12,6)</span><span class="sxs-lookup"><span data-stu-id="1414a-125">BITXOR(12,6)</span></span>
  
<span data-ttu-id="1414a-p103">返回 10。12 = 0...01100。6 = 0...00110。因此，BITXOR(12,6) = 0...01010。</span><span class="sxs-lookup"><span data-stu-id="1414a-p103">Returns 10. The 12 = 0...01100. The 6 = 0...00110. Therefore, BITXOR(12,6) = 0...01010.</span></span>
  

