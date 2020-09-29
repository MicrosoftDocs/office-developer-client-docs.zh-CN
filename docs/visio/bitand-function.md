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
description: 返回一个16位二进制数，只有在 binarynumber1 和 binarynumber2 中的相应位为1时，才将每位的二进制数设置为1。 否则，将位设置为0。
ms.openlocfilehash: a3c76a9122d0f02d5ab61460cf3457bb15da4d7b
ms.sourcegitcommit: 939bd9686ba41a8f94b82e004ed84b9054d9c7cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48293490"
---
# <a name="bitand-function"></a><span data-ttu-id="20d2f-104">BITAND 函数</span><span class="sxs-lookup"><span data-stu-id="20d2f-104">BITAND Function</span></span>

<span data-ttu-id="20d2f-105">返回一个16位二进制数，只有在 binarynumber1 和 binarynumber2 中的相应位为1时，才将每位的二进制数设置为1。</span><span class="sxs-lookup"><span data-stu-id="20d2f-105">Returns a 16-bit binary number in which each bit is set to 1 only if the corresponding bit in both binarynumber1 and binarynumber2 is 1.</span></span> <span data-ttu-id="20d2f-106">否则，将位设置为0。</span><span class="sxs-lookup"><span data-stu-id="20d2f-106">Otherwise, the bit is set to 0.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="20d2f-107">语法</span><span class="sxs-lookup"><span data-stu-id="20d2f-107">Syntax</span></span>

<span data-ttu-id="20d2f-108">BITAND (***binarynumber1***， ***binarynumber2*** ) </span><span class="sxs-lookup"><span data-stu-id="20d2f-108">BITAND(***binarynumber1***, ***binarynumber2*** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="20d2f-109">参数</span><span class="sxs-lookup"><span data-stu-id="20d2f-109">Parameters</span></span>

|<span data-ttu-id="20d2f-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="20d2f-110">**Name**</span></span>|<span data-ttu-id="20d2f-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="20d2f-111">**Required/Optional**</span></span>|<span data-ttu-id="20d2f-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="20d2f-112">**Data Type**</span></span>|<span data-ttu-id="20d2f-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="20d2f-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="20d2f-114">_二进制数字1_</span><span class="sxs-lookup"><span data-stu-id="20d2f-114">_binary number1_</span></span> <br/> |<span data-ttu-id="20d2f-115">必需</span><span class="sxs-lookup"><span data-stu-id="20d2f-115">Required</span></span>  <br/> |<span data-ttu-id="20d2f-116">**数值**</span><span class="sxs-lookup"><span data-stu-id="20d2f-116">**Numeric**</span></span> <br/> |<span data-ttu-id="20d2f-117">第一个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="20d2f-117">The first 16-bit binary number.</span></span>  <br/> |
| <span data-ttu-id="20d2f-118">_二进制数字2_</span><span class="sxs-lookup"><span data-stu-id="20d2f-118">_binary number2_</span></span> <br/> |<span data-ttu-id="20d2f-119">必需</span><span class="sxs-lookup"><span data-stu-id="20d2f-119">Required</span></span>  <br/> |<span data-ttu-id="20d2f-120">**数值**</span><span class="sxs-lookup"><span data-stu-id="20d2f-120">**Numeric**</span></span> <br/> |<span data-ttu-id="20d2f-121">第二个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="20d2f-121">The second 16-bit binary number.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="20d2f-122">说明</span><span class="sxs-lookup"><span data-stu-id="20d2f-122">Remarks</span></span>

<span data-ttu-id="20d2f-123">可使用此函数测试和更改那些存储为位掩码（例如形状的文本格式）的形状的属性。</span><span class="sxs-lookup"><span data-stu-id="20d2f-123">You can use this function to test and change properties of a shape that are stored as bitmasks, for example, the shape's text format.</span></span>
  
## <a name="example"></a><span data-ttu-id="20d2f-124">示例</span><span class="sxs-lookup"><span data-stu-id="20d2f-124">Example</span></span>

<span data-ttu-id="20d2f-125">BITAND (12，6) </span><span class="sxs-lookup"><span data-stu-id="20d2f-125">BITAND(12,6)</span></span>
  
<span data-ttu-id="20d2f-p103">返回 4。12 = 0...01100。6 = 0...00110。因此，BITAND(12,6) = 0...00100。</span><span class="sxs-lookup"><span data-stu-id="20d2f-p103">Returns 4. The 12 = 0...01100. The 6 = 0...00110. Therefore, BITAND(12,6) = 0...00100.</span></span>
  

