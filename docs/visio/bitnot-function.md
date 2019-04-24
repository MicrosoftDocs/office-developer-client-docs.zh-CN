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
description: 返回一个16位二进制数, 只有当二进制数中的对应位为0时, 才将每位的二进制数设置为1。 否则, 将位设置为0。
ms.openlocfilehash: 34ea6fd614feae8e3c8e97e34b7ff6c531f4c123
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330007"
---
# <a name="bitnot-function"></a><span data-ttu-id="e7979-104">BITNOT 函数</span><span class="sxs-lookup"><span data-stu-id="e7979-104">BITNOT Function</span></span>

<span data-ttu-id="e7979-105">返回一个16位二进制数, 只有当二进制数中的对应位为0时, 才将每位的二进制数设置为1。</span><span class="sxs-lookup"><span data-stu-id="e7979-105">Returns a 16-bit binary number in which each bit is set to 1 only if the corresponding bit in binary number is 0.</span></span> <span data-ttu-id="e7979-106">否则, 将位设置为0。</span><span class="sxs-lookup"><span data-stu-id="e7979-106">Otherwise, the bit is set to 0.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="e7979-107">语法</span><span class="sxs-lookup"><span data-stu-id="e7979-107">Syntax</span></span>

<span data-ttu-id="e7979-108">BITNOT (\* **二进制数** \*)</span><span class="sxs-lookup"><span data-stu-id="e7979-108">BITNOT(\*\* *binary number* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="e7979-109">参数</span><span class="sxs-lookup"><span data-stu-id="e7979-109">Parameters</span></span>

|<span data-ttu-id="e7979-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="e7979-110">**Name**</span></span>|<span data-ttu-id="e7979-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="e7979-111">**Required/Optional**</span></span>|<span data-ttu-id="e7979-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e7979-112">**Data Type**</span></span>|<span data-ttu-id="e7979-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="e7979-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e7979-114">_二进制数_</span><span class="sxs-lookup"><span data-stu-id="e7979-114">_binary number_</span></span> <br/> |<span data-ttu-id="e7979-115">必需</span><span class="sxs-lookup"><span data-stu-id="e7979-115">Required</span></span>  <br/> |<span data-ttu-id="e7979-116">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="e7979-116">**Numeric**</span></span> <br/> |<span data-ttu-id="e7979-117">一个 16 位二进制数。</span><span class="sxs-lookup"><span data-stu-id="e7979-117">A 16-bit binary number.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="e7979-118">返回值</span><span class="sxs-lookup"><span data-stu-id="e7979-118">Return value</span></span>

<span data-ttu-id="e7979-119">16 位二进制数</span><span class="sxs-lookup"><span data-stu-id="e7979-119">16-bit Binary</span></span>
  
## <a name="example"></a><span data-ttu-id="e7979-120">示例</span><span class="sxs-lookup"><span data-stu-id="e7979-120">Example</span></span>

<span data-ttu-id="e7979-121">BITNOT (6)</span><span class="sxs-lookup"><span data-stu-id="e7979-121">BITNOT(6)</span></span>
  
<span data-ttu-id="e7979-p103">返回 65529。6 = 0...00110。因此，BITNOT(6) = 1...11001。</span><span class="sxs-lookup"><span data-stu-id="e7979-p103">Returns 65529. The 6 = 0...00110. Therefore, BITNOT(6) = 1...11001.</span></span>
  

