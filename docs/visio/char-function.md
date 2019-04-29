---
title: CHAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251406
localization_priority: Normal
ms.assetid: 0803d5d3-d804-5ffe-604d-661b35d1fc01
description: 返回一个数字的 ANSI 字符。
ms.openlocfilehash: 6f1c459892331ec30ad93bbc860fcd038e8f4732
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418188"
---
# <a name="char-function"></a><span data-ttu-id="34b70-103">CHAR 函数</span><span class="sxs-lookup"><span data-stu-id="34b70-103">CHAR Function</span></span>

<span data-ttu-id="34b70-104">返回一个数字的 ANSI 字符。</span><span class="sxs-lookup"><span data-stu-id="34b70-104">Returns the ANSI character for a number.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="34b70-105">语法</span><span class="sxs-lookup"><span data-stu-id="34b70-105">Syntax</span></span>

<span data-ttu-id="34b70-106">CHAR (\* \* *number* \* \*)</span><span class="sxs-lookup"><span data-stu-id="34b70-106">CHAR(\*\* *number* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="34b70-107">参数</span><span class="sxs-lookup"><span data-stu-id="34b70-107">Parameters</span></span>

|<span data-ttu-id="34b70-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="34b70-108">**Name**</span></span>|<span data-ttu-id="34b70-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="34b70-109">**Required/Optional**</span></span>|<span data-ttu-id="34b70-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="34b70-110">**Data Type**</span></span>|<span data-ttu-id="34b70-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="34b70-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="34b70-112">_number_</span><span class="sxs-lookup"><span data-stu-id="34b70-112">_number_</span></span> <br/> |<span data-ttu-id="34b70-113">必需</span><span class="sxs-lookup"><span data-stu-id="34b70-113">Required</span></span>  <br/> |<span data-ttu-id="34b70-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="34b70-114">**Number**</span></span> <br/> |<span data-ttu-id="34b70-115">要获取其 ANSI 字符的数字。</span><span class="sxs-lookup"><span data-stu-id="34b70-115">The number whose ANSI character you want to get.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="34b70-116">说明</span><span class="sxs-lookup"><span data-stu-id="34b70-116">Remarks</span></span>

<span data-ttu-id="34b70-117">结果字符串的长度为一个字符。</span><span class="sxs-lookup"><span data-stu-id="34b70-117">The resulting string is one character in length.</span></span> <span data-ttu-id="34b70-118">number 参数必须是介于1和255之间的整数 (含这两个_值_), 否则函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="34b70-118">The  _number_ parameter must be an integer between 1 and 255 (inclusive), or the function returns an error.</span></span> 
  
## <a name="example"></a><span data-ttu-id="34b70-119">示例</span><span class="sxs-lookup"><span data-stu-id="34b70-119">Example</span></span>

<span data-ttu-id="34b70-120">CHAR (9)</span><span class="sxs-lookup"><span data-stu-id="34b70-120">CHAR(9)</span></span> 
  
<span data-ttu-id="34b70-121">返回制表符。</span><span class="sxs-lookup"><span data-stu-id="34b70-121">Returns the tab character.</span></span> 
  

