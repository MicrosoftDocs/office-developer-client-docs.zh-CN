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
description: 返回一个 16 位二进制数，只有当 binarynumber1 和 binarynumber2 中的对应位都为 1 时，每个位才被设置为 1。 否则，将位设置为 0。
ms.openlocfilehash: a3c76a9122d0f02d5ab61460cf3457bb15da4d7b
ms.sourcegitcommit: 939bd9686ba41a8f94b82e004ed84b9054d9c7cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48293490"
---
# <a name="bitand-function"></a><span data-ttu-id="517b7-104">BITAND 函数</span><span class="sxs-lookup"><span data-stu-id="517b7-104">BITAND Function</span></span>

<span data-ttu-id="517b7-105">返回一个 16 位二进制数，只有当 binarynumber1 和 binarynumber2 中的对应位都为 1 时，每个位才被设置为 1。</span><span class="sxs-lookup"><span data-stu-id="517b7-105">Returns a 16-bit binary number in which each bit is set to 1 only if the corresponding bit in both binarynumber1 and binarynumber2 is 1.</span></span> <span data-ttu-id="517b7-106">否则，将位设置为 0。</span><span class="sxs-lookup"><span data-stu-id="517b7-106">Otherwise, the bit is set to 0.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="517b7-107">语法</span><span class="sxs-lookup"><span data-stu-id="517b7-107">Syntax</span></span>

<span data-ttu-id="517b7-108">BITAND (***binarynumber1***、 ***binarynumber2*** ) </span><span class="sxs-lookup"><span data-stu-id="517b7-108">BITAND(***binarynumber1***, ***binarynumber2*** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="517b7-109">参数</span><span class="sxs-lookup"><span data-stu-id="517b7-109">Parameters</span></span>

|<span data-ttu-id="517b7-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="517b7-110">**Name**</span></span>|<span data-ttu-id="517b7-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="517b7-111">**Required/Optional**</span></span>|<span data-ttu-id="517b7-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="517b7-112">**Data Type**</span></span>|<span data-ttu-id="517b7-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="517b7-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="517b7-114">_binary number1_</span><span class="sxs-lookup"><span data-stu-id="517b7-114">_binary number1_</span></span> <br/> |<span data-ttu-id="517b7-115">必需</span><span class="sxs-lookup"><span data-stu-id="517b7-115">Required</span></span>  <br/> |<span data-ttu-id="517b7-116">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="517b7-116">**Numeric**</span></span> <br/> |<span data-ttu-id="517b7-117">第一个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="517b7-117">The first 16-bit binary number.</span></span>  <br/> |
| <span data-ttu-id="517b7-118">_binary number2_</span><span class="sxs-lookup"><span data-stu-id="517b7-118">_binary number2_</span></span> <br/> |<span data-ttu-id="517b7-119">必需</span><span class="sxs-lookup"><span data-stu-id="517b7-119">Required</span></span>  <br/> |<span data-ttu-id="517b7-120">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="517b7-120">**Numeric**</span></span> <br/> |<span data-ttu-id="517b7-121">第二个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="517b7-121">The second 16-bit binary number.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="517b7-122">备注</span><span class="sxs-lookup"><span data-stu-id="517b7-122">Remarks</span></span>

<span data-ttu-id="517b7-123">可使用此函数测试和更改那些存储为位掩码（例如形状的文本格式）的形状的属性。</span><span class="sxs-lookup"><span data-stu-id="517b7-123">You can use this function to test and change properties of a shape that are stored as bitmasks, for example, the shape's text format.</span></span>
  
## <a name="example"></a><span data-ttu-id="517b7-124">示例</span><span class="sxs-lookup"><span data-stu-id="517b7-124">Example</span></span>

<span data-ttu-id="517b7-125">BITAND (12，6) </span><span class="sxs-lookup"><span data-stu-id="517b7-125">BITAND(12,6)</span></span>
  
<span data-ttu-id="517b7-p103">返回 4。12 = 0...01100。6 = 0...00110。因此，BITAND(12,6) = 0...00100。</span><span class="sxs-lookup"><span data-stu-id="517b7-p103">Returns 4. The 12 = 0...01100. The 6 = 0...00110. Therefore, BITAND(12,6) = 0...00100.</span></span>
  

