---
title: LOWER 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251459
localization_priority: Normal
ms.assetid: 1d198ea6-49e0-e462-b2cf-b65fbb920b55
description: 返回转换为小写字母的字符串。
ms.openlocfilehash: 275e5cc40bed5c3ca7d6f40b0882f523334611c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421240"
---
# <a name="lower-function"></a><span data-ttu-id="8d330-103">LOWER 函数</span><span class="sxs-lookup"><span data-stu-id="8d330-103">LOWER Function</span></span>

<span data-ttu-id="8d330-104">返回转换为小写字母的字符串。</span><span class="sxs-lookup"><span data-stu-id="8d330-104">Returns a string converted to lowercase.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8d330-105">语法</span><span class="sxs-lookup"><span data-stu-id="8d330-105">Syntax</span></span>

<span data-ttu-id="8d330-106">LOWER (\*\* *expression* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="8d330-106">LOWER(\*\* *expression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="8d330-107">参数</span><span class="sxs-lookup"><span data-stu-id="8d330-107">Parameters</span></span>

|<span data-ttu-id="8d330-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="8d330-108">**Name**</span></span>|<span data-ttu-id="8d330-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="8d330-109">**Required/Optional**</span></span>|<span data-ttu-id="8d330-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8d330-110">**Data Type**</span></span>|<span data-ttu-id="8d330-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="8d330-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8d330-112">_expression_</span><span class="sxs-lookup"><span data-stu-id="8d330-112">_expression_</span></span> <br/> |<span data-ttu-id="8d330-113">必需</span><span class="sxs-lookup"><span data-stu-id="8d330-113">Required</span></span>  <br/> |<span data-ttu-id="8d330-114">**变化**</span><span class="sxs-lookup"><span data-stu-id="8d330-114">**Varies**</span></span> <br/> | <span data-ttu-id="8d330-115">字符串、单元格引用或表达式；结果转换为字符串，然后再转换为小写形式。</span><span class="sxs-lookup"><span data-stu-id="8d330-115">A string, a cell reference, or an expression; the result is converted to a string which is then converted to lowercase.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="8d330-116">返回值</span><span class="sxs-lookup"><span data-stu-id="8d330-116">Return value</span></span>

<span data-ttu-id="8d330-117">String</span><span class="sxs-lookup"><span data-stu-id="8d330-117">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8d330-118">备注</span><span class="sxs-lookup"><span data-stu-id="8d330-118">Remarks</span></span>

<span data-ttu-id="8d330-119">大小写转换取决于当前的用户设置，并且特定于区域设置。</span><span class="sxs-lookup"><span data-stu-id="8d330-119">The case conversion is locale-specific, based on the current user settings.</span></span> 
  
## <a name="example"></a><span data-ttu-id="8d330-120">示例</span><span class="sxs-lookup"><span data-stu-id="8d330-120">Example</span></span>

<span data-ttu-id="8d330-121">LOWER("mIxEd CAse")</span><span class="sxs-lookup"><span data-stu-id="8d330-121">LOWER("mIxEd CAse")</span></span> 
  
<span data-ttu-id="8d330-122">返回“mixed case”。</span><span class="sxs-lookup"><span data-stu-id="8d330-122">Returns "mixed case".</span></span> 
  

