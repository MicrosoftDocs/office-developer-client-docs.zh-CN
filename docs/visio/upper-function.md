---
title: UPPER 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251509
localization_priority: Normal
ms.assetid: ef94ee0f-dbb8-a2e1-1805-8a6609830d2a
description: 返回一个转换为大写的字符串。
ms.openlocfilehash: b88958526bfb5e08839077217759f7ffb50151b0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327326"
---
# <a name="upper-function"></a><span data-ttu-id="f646f-103">UPPER 函数</span><span class="sxs-lookup"><span data-stu-id="f646f-103">UPPER Function</span></span>

<span data-ttu-id="f646f-104">返回一个转换为大写的字符串。</span><span class="sxs-lookup"><span data-stu-id="f646f-104">Returns a string converted to uppercase.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f646f-105">语法</span><span class="sxs-lookup"><span data-stu-id="f646f-105">Syntax</span></span>

<span data-ttu-id="f646f-106">UPPER (\* **表达式** \*)</span><span class="sxs-lookup"><span data-stu-id="f646f-106">UPPER(\*\* *expression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="f646f-107">参数</span><span class="sxs-lookup"><span data-stu-id="f646f-107">Parameters</span></span>

|<span data-ttu-id="f646f-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="f646f-108">**Name**</span></span>|<span data-ttu-id="f646f-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f646f-109">**Required/Optional**</span></span>|<span data-ttu-id="f646f-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f646f-110">**Data Type**</span></span>|<span data-ttu-id="f646f-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f646f-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f646f-112">_expression_</span><span class="sxs-lookup"><span data-stu-id="f646f-112">_expression_</span></span> <br/> |<span data-ttu-id="f646f-113">必需</span><span class="sxs-lookup"><span data-stu-id="f646f-113">Required</span></span>  <br/> |<span data-ttu-id="f646f-114">**相同**</span><span class="sxs-lookup"><span data-stu-id="f646f-114">**Varies**</span></span> <br/> | <span data-ttu-id="f646f-115">可以是字符串、单元格引用或表达式；结果转换为字符串，然后再转换为大写形式。</span><span class="sxs-lookup"><span data-stu-id="f646f-115">A string, a cell reference, or an expression; the result is converted to a string, which is then converted to uppercase.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f646f-116">注解</span><span class="sxs-lookup"><span data-stu-id="f646f-116">Remarks</span></span>

<span data-ttu-id="f646f-117">大小写转换取决于当前的用户设置，并且特定于区域设置。</span><span class="sxs-lookup"><span data-stu-id="f646f-117">The case conversion is locale-specific, based on the current user settings.</span></span> 
  
## <a name="example"></a><span data-ttu-id="f646f-118">示例</span><span class="sxs-lookup"><span data-stu-id="f646f-118">Example</span></span>

<span data-ttu-id="f646f-119">UPPER("mIxEd CAse")</span><span class="sxs-lookup"><span data-stu-id="f646f-119">UPPER("mIxEd CAse")</span></span> 
  
<span data-ttu-id="f646f-120">返回“MIXED CASE”。</span><span class="sxs-lookup"><span data-stu-id="f646f-120">Returns "MIXED CASE".</span></span> 
  

