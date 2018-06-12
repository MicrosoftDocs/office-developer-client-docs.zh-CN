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
description: 返回其中每个位设置为 1 如果二进制 number1 或二进制数字 2 中相应的位为 1 16 位二进制数。 仅当二进制 number1 和二进制数字 2 中的相应的位是 0 位设置为 0。
ms.openlocfilehash: db9808f16b32776149abbddf882310c02268cec3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779734"
---
# <a name="bitor-function"></a><span data-ttu-id="d1d06-104">BITOR 函数</span><span class="sxs-lookup"><span data-stu-id="d1d06-104">BITOR Function</span></span>

<span data-ttu-id="d1d06-105">返回其中每个位设置为 1 如果*二进制 number1*或*二进制数字 2*中相应的位为 1 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="d1d06-105">Returns a 16-bit binary number in which each bit is set to 1 if the corresponding bit in either  *binary number1*  or  *binary number2*  is 1.</span></span> <span data-ttu-id="d1d06-106">仅当相应的位*二进制 number1*和*二进制数字 2*中的 0 位设置为 0。</span><span class="sxs-lookup"><span data-stu-id="d1d06-106">The bit is set to 0 only if the corresponding bit is 0 in both  *binary number1*  and  *binary number2*  .</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d1d06-107">语法</span><span class="sxs-lookup"><span data-stu-id="d1d06-107">Syntax</span></span>

<span data-ttu-id="d1d06-108">BITOR (* **二进制数字 1* * *，* **二进制数字 2* * *)</span><span class="sxs-lookup"><span data-stu-id="d1d06-108">BITOR(** *binary number1* **, ** *binary number2* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d1d06-109">参数</span><span class="sxs-lookup"><span data-stu-id="d1d06-109">Parameters</span></span>

|<span data-ttu-id="d1d06-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="d1d06-110">**Name**</span></span>|<span data-ttu-id="d1d06-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d1d06-111">**Required/Optional**</span></span>|<span data-ttu-id="d1d06-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d1d06-112">**Data Type**</span></span>|<span data-ttu-id="d1d06-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1d06-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d1d06-114">_二进制 number1_</span><span class="sxs-lookup"><span data-stu-id="d1d06-114">_binary number1_</span></span> <br/> |<span data-ttu-id="d1d06-115">必需</span><span class="sxs-lookup"><span data-stu-id="d1d06-115">Required</span></span>  <br/> |<span data-ttu-id="d1d06-116">**数字**</span><span class="sxs-lookup"><span data-stu-id="d1d06-116">**Numeric**</span></span> <br/> |<span data-ttu-id="d1d06-117">第一个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="d1d06-117">The first 16-bit binary number.</span></span>  <br/> |
| <span data-ttu-id="d1d06-118">_二进制数字 2_</span><span class="sxs-lookup"><span data-stu-id="d1d06-118">_binary number2_</span></span> <br/> |<span data-ttu-id="d1d06-119">必需</span><span class="sxs-lookup"><span data-stu-id="d1d06-119">Required</span></span>  <br/> |<span data-ttu-id="d1d06-120">**数字**</span><span class="sxs-lookup"><span data-stu-id="d1d06-120">**Numeric**</span></span> <br/> |<span data-ttu-id="d1d06-121">第二个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="d1d06-121">The second 16-bit binary number.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="d1d06-122">返回值</span><span class="sxs-lookup"><span data-stu-id="d1d06-122">Return value</span></span>

<span data-ttu-id="d1d06-123">16 位二进制数</span><span class="sxs-lookup"><span data-stu-id="d1d06-123">16-bit Binary</span></span>
  
## <a name="example"></a><span data-ttu-id="d1d06-124">示例</span><span class="sxs-lookup"><span data-stu-id="d1d06-124">Example</span></span>

<span data-ttu-id="d1d06-125">BITOR(12,6)</span><span class="sxs-lookup"><span data-stu-id="d1d06-125">BITOR(12,6)</span></span>
  
<span data-ttu-id="d1d06-p103">返回 14。12 = 0...01100。6 = 0...00110。因此，BITOR(12,6) = 0...01110。</span><span class="sxs-lookup"><span data-stu-id="d1d06-p103">Returns 14. The 12 = 0...01100. The 6 = 0...00110. Therefore, BITOR(12,6) = 0...01110.</span></span>
  

