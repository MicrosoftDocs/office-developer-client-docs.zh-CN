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
description: 返回一个16位二进制数, 其中如果二进制数字1或二进制数字2中的相应位为 1, 则将每位的二进制数设置为1。 仅当二进制数字1和二进制数字2中对应的位为0时, 位才设置为0。
ms.openlocfilehash: 13bda2c6c65557b1f8372432cf919b2aaf2d75de
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303372"
---
# <a name="bitor-function"></a><span data-ttu-id="2c3b4-104">BITOR 函数</span><span class="sxs-lookup"><span data-stu-id="2c3b4-104">BITOR Function</span></span>

<span data-ttu-id="2c3b4-105">返回一个16位二进制数, 其中如果*二进制*数字1或*二进制数字 2*中的相应位为 1, 则将每位的二进制数设置为1。</span><span class="sxs-lookup"><span data-stu-id="2c3b4-105">Returns a 16-bit binary number in which each bit is set to 1 if the corresponding bit in either  *binary number1*  or  *binary number2*  is 1.</span></span> <span data-ttu-id="2c3b4-106">仅当*二进制数字 1*和*二进制数字 2*中对应的位为0时, 位才设置为0。</span><span class="sxs-lookup"><span data-stu-id="2c3b4-106">The bit is set to 0 only if the corresponding bit is 0 in both  *binary number1*  and  *binary number2*  .</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="2c3b4-107">语法</span><span class="sxs-lookup"><span data-stu-id="2c3b4-107">Syntax</span></span>

<span data-ttu-id="2c3b4-108">BITOR (\* \* *binary 1* \* \*, \* \**二进制数字 2* \* \*)</span><span class="sxs-lookup"><span data-stu-id="2c3b4-108">BITOR(\*\* *binary number1* \*\*, \*\* *binary number2* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="2c3b4-109">参数</span><span class="sxs-lookup"><span data-stu-id="2c3b4-109">Parameters</span></span>

|<span data-ttu-id="2c3b4-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="2c3b4-110">**Name**</span></span>|<span data-ttu-id="2c3b4-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="2c3b4-111">**Required/Optional**</span></span>|<span data-ttu-id="2c3b4-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2c3b4-112">**Data Type**</span></span>|<span data-ttu-id="2c3b4-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c3b4-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2c3b4-114">_二进制数字1_</span><span class="sxs-lookup"><span data-stu-id="2c3b4-114">_binary number1_</span></span> <br/> |<span data-ttu-id="2c3b4-115">必需</span><span class="sxs-lookup"><span data-stu-id="2c3b4-115">Required</span></span>  <br/> |<span data-ttu-id="2c3b4-116">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="2c3b4-116">**Numeric**</span></span> <br/> |<span data-ttu-id="2c3b4-117">第一个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="2c3b4-117">The first 16-bit binary number.</span></span>  <br/> |
| <span data-ttu-id="2c3b4-118">_二进制数字2_</span><span class="sxs-lookup"><span data-stu-id="2c3b4-118">_binary number2_</span></span> <br/> |<span data-ttu-id="2c3b4-119">必需</span><span class="sxs-lookup"><span data-stu-id="2c3b4-119">Required</span></span>  <br/> |<span data-ttu-id="2c3b4-120">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="2c3b4-120">**Numeric**</span></span> <br/> |<span data-ttu-id="2c3b4-121">第二个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="2c3b4-121">The second 16-bit binary number.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="2c3b4-122">返回值</span><span class="sxs-lookup"><span data-stu-id="2c3b4-122">Return value</span></span>

<span data-ttu-id="2c3b4-123">16 位二进制数</span><span class="sxs-lookup"><span data-stu-id="2c3b4-123">16-bit Binary</span></span>
  
## <a name="example"></a><span data-ttu-id="2c3b4-124">示例</span><span class="sxs-lookup"><span data-stu-id="2c3b4-124">Example</span></span>

<span data-ttu-id="2c3b4-125">BITOR (12, 6)</span><span class="sxs-lookup"><span data-stu-id="2c3b4-125">BITOR(12,6)</span></span>
  
<span data-ttu-id="2c3b4-p103">返回 14。12 = 0...01100。6 = 0...00110。因此，BITOR(12,6) = 0...01110。</span><span class="sxs-lookup"><span data-stu-id="2c3b4-p103">Returns 14. The 12 = 0...01100. The 6 = 0...00110. Therefore, BITOR(12,6) = 0...01110.</span></span>
  

