---
title: BITAND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251398
localization_priority: Normal
ms.assetid: c437de23-d2e0-469d-62e6-8eb8b8cfea5c
description: 返回其中每个位设置为 1 binarynumber1 和 binarynumber2 中相应的位为 1 时才是 16 位二进制数。 否则，将位设置为 0。
ms.openlocfilehash: 0b501bb383596e3f2f39ea14f2cb9eb4bf40b25b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779742"
---
# <a name="bitand-function"></a><span data-ttu-id="45065-104">BITAND 函数</span><span class="sxs-lookup"><span data-stu-id="45065-104">BITAND Function</span></span>

<span data-ttu-id="45065-105">返回其中每个位设置为 1 binarynumber1 和 binarynumber2 中相应的位为 1 时才是 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="45065-105">Returns a 16-bit binary number in which each bit is set to 1 only if the corresponding bit in both binarynumber1 and binarynumber2 is 1.</span></span> <span data-ttu-id="45065-106">否则，将位设置为 0。</span><span class="sxs-lookup"><span data-stu-id="45065-106">Otherwise, the bit is set to 0.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="45065-107">语法</span><span class="sxs-lookup"><span data-stu-id="45065-107">Syntax</span></span>

<span data-ttu-id="45065-108">BITAND (* * *binarynumber1* * *，* * *binarynumber2* * *)</span><span class="sxs-lookup"><span data-stu-id="45065-108">BITAND(** *binarynumber1* **, ** *binarynumber2* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="45065-109">参数</span><span class="sxs-lookup"><span data-stu-id="45065-109">Parameters</span></span>

|<span data-ttu-id="45065-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="45065-110">**Name**</span></span>|<span data-ttu-id="45065-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="45065-111">**Required/Optional**</span></span>|<span data-ttu-id="45065-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="45065-112">**Data Type**</span></span>|<span data-ttu-id="45065-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="45065-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="45065-114">_二进制 number1_</span><span class="sxs-lookup"><span data-stu-id="45065-114">_binary number1_</span></span> <br/> |<span data-ttu-id="45065-115">必需</span><span class="sxs-lookup"><span data-stu-id="45065-115">Required</span></span>  <br/> |<span data-ttu-id="45065-116">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="45065-116">**Numeric**</span></span> <br/> |<span data-ttu-id="45065-117">第一个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="45065-117">The first 16-bit binary number.</span></span>  <br/> |
| <span data-ttu-id="45065-118">_二进制数字 2_</span><span class="sxs-lookup"><span data-stu-id="45065-118">_binary number2_</span></span> <br/> |<span data-ttu-id="45065-119">必需</span><span class="sxs-lookup"><span data-stu-id="45065-119">Required</span></span>  <br/> |<span data-ttu-id="45065-120">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="45065-120">**Numeric**</span></span> <br/> |<span data-ttu-id="45065-121">第二个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="45065-121">The second 16-bit binary number.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="45065-122">注解</span><span class="sxs-lookup"><span data-stu-id="45065-122">Remarks</span></span>

<span data-ttu-id="45065-123">可使用此函数测试和更改那些存储为位掩码（例如形状的文本格式）的形状的属性。</span><span class="sxs-lookup"><span data-stu-id="45065-123">You can use this function to test and change properties of a shape that are stored as bitmasks, for example, the shape's text format.</span></span>
  
## <a name="example"></a><span data-ttu-id="45065-124">示例</span><span class="sxs-lookup"><span data-stu-id="45065-124">Example</span></span>

<span data-ttu-id="45065-125">BITAND(12,6)</span><span class="sxs-lookup"><span data-stu-id="45065-125">BITAND(12,6)</span></span>
  
<span data-ttu-id="45065-p103">返回 4。12 = 0...01100。6 = 0...00110。因此，BITAND(12,6) = 0...00100。</span><span class="sxs-lookup"><span data-stu-id="45065-p103">Returns 4. The 12 = 0...01100. The 6 = 0...00110. Therefore, BITAND(12,6) = 0...00100.</span></span>
  

