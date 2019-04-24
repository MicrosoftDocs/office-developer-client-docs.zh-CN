---
title: UNICHAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60117
localization_priority: Normal
ms.assetid: 371a475d-50f7-6b4c-4b47-581cd778dcba
description: 从数字中返回 Unicode 字符。
ms.openlocfilehash: 81e76b72da35f79dee9ad6afbde51bc2e228483c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327344"
---
# <a name="unichar-function"></a><span data-ttu-id="2eb51-103">UNICHAR 函数</span><span class="sxs-lookup"><span data-stu-id="2eb51-103">UNICHAR Function</span></span>

<span data-ttu-id="2eb51-104">从数字中返回 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="2eb51-104">Returns the Unicode character from a number.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="2eb51-105">语法</span><span class="sxs-lookup"><span data-stu-id="2eb51-105">Syntax</span></span>

<span data-ttu-id="2eb51-106">UNICHAR (\* **数字** \*)</span><span class="sxs-lookup"><span data-stu-id="2eb51-106">UNICHAR (\*\* *number* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="2eb51-107">参数</span><span class="sxs-lookup"><span data-stu-id="2eb51-107">Parameters</span></span>

|<span data-ttu-id="2eb51-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="2eb51-108">**Name**</span></span>|<span data-ttu-id="2eb51-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="2eb51-109">**Required/Optional**</span></span>|<span data-ttu-id="2eb51-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2eb51-110">**Data Type**</span></span>|<span data-ttu-id="2eb51-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="2eb51-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2eb51-112">_number_</span><span class="sxs-lookup"><span data-stu-id="2eb51-112">_number_</span></span> <br/> |<span data-ttu-id="2eb51-113">必需</span><span class="sxs-lookup"><span data-stu-id="2eb51-113">Required</span></span>  <br/> |<span data-ttu-id="2eb51-114">**Integer**</span><span class="sxs-lookup"><span data-stu-id="2eb51-114">**Integer**</span></span> <br/> |<span data-ttu-id="2eb51-115">1 到 65,535 之间（包括 1 和 65,535）的整数，若超出此范围，该函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="2eb51-115">An integer between 1 and 65,535 (inclusive), or the function returns an error.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2eb51-116">注解</span><span class="sxs-lookup"><span data-stu-id="2eb51-116">Remarks</span></span>

<span data-ttu-id="2eb51-117">生成的字符串的长度为一个 Unicode 字符（两个字符）。</span><span class="sxs-lookup"><span data-stu-id="2eb51-117">The resulting string is one Unicode character (two characters) in length.</span></span> 
  
## <a name="example"></a><span data-ttu-id="2eb51-118">示例</span><span class="sxs-lookup"><span data-stu-id="2eb51-118">Example</span></span>

<span data-ttu-id="2eb51-119">UNICHAR (65)</span><span class="sxs-lookup"><span data-stu-id="2eb51-119">UNICHAR(65)</span></span> 
  
<span data-ttu-id="2eb51-120">返回 A (拉丁文大写字母 A)</span><span class="sxs-lookup"><span data-stu-id="2eb51-120">Returns A (Latin Capital Letter A)</span></span> 
  

