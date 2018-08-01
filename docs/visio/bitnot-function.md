---
title: BITNOT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251399
localization_priority: Normal
ms.assetid: 7b6486bb-3618-3747-4b00-93bd55767c1c
description: 返回其中每个位设置为 1 中的二进制数相应的位为 0 时才是 16 位二进制数。 否则，将位设置为 0。
ms.openlocfilehash: 0806e7c52cab659a09d27a60efb9c09aa436fb92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779717"
---
# <a name="bitnot-function"></a><span data-ttu-id="b2e5a-104">BITNOT 函数</span><span class="sxs-lookup"><span data-stu-id="b2e5a-104">BITNOT Function</span></span>

<span data-ttu-id="b2e5a-105">返回其中每个位设置为 1 中的二进制数相应的位为 0 时才是 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-105">Returns a 16-bit binary number in which each bit is set to 1 only if the corresponding bit in binary number is 0.</span></span> <span data-ttu-id="b2e5a-106">否则，将位设置为 0。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-106">Otherwise, the bit is set to 0.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="b2e5a-107">语法</span><span class="sxs-lookup"><span data-stu-id="b2e5a-107">Syntax</span></span>

<span data-ttu-id="b2e5a-108">BITNOT (* **二进制数** *)</span><span class="sxs-lookup"><span data-stu-id="b2e5a-108">BITNOT(** *binary number* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="b2e5a-109">参数</span><span class="sxs-lookup"><span data-stu-id="b2e5a-109">Parameters</span></span>

|<span data-ttu-id="b2e5a-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="b2e5a-110">**Name**</span></span>|<span data-ttu-id="b2e5a-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="b2e5a-111">**Required/Optional**</span></span>|<span data-ttu-id="b2e5a-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b2e5a-112">**Data Type**</span></span>|<span data-ttu-id="b2e5a-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="b2e5a-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b2e5a-114">_二进制数_</span><span class="sxs-lookup"><span data-stu-id="b2e5a-114">_binary number_</span></span> <br/> |<span data-ttu-id="b2e5a-115">必需</span><span class="sxs-lookup"><span data-stu-id="b2e5a-115">Required</span></span>  <br/> |<span data-ttu-id="b2e5a-116">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="b2e5a-116">**Numeric**</span></span> <br/> |<span data-ttu-id="b2e5a-117">一个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-117">A 16-bit binary number.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="b2e5a-118">返回值</span><span class="sxs-lookup"><span data-stu-id="b2e5a-118">Return value</span></span>

<span data-ttu-id="b2e5a-119">16 位二进制数</span><span class="sxs-lookup"><span data-stu-id="b2e5a-119">16-bit Binary</span></span>
  
## <a name="example"></a><span data-ttu-id="b2e5a-120">示例</span><span class="sxs-lookup"><span data-stu-id="b2e5a-120">Example</span></span>

<span data-ttu-id="b2e5a-121">BITNOT(6)</span><span class="sxs-lookup"><span data-stu-id="b2e5a-121">BITNOT(6)</span></span>
  
<span data-ttu-id="b2e5a-p103">返回 65529。6 = 0...00110。因此，BITNOT(6) = 1...11001。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-p103">Returns 65529. The 6 = 0...00110. Therefore, BITNOT(6) = 1...11001.</span></span>
  

