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
description: 返回数字的 Unicode 字符。
ms.openlocfilehash: 06f97717ee4d5965253b0da7cfd5c35faf0ca2f7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781596"
---
# <a name="unichar-function"></a><span data-ttu-id="2eb1c-103">UNICHAR 函数</span><span class="sxs-lookup"><span data-stu-id="2eb1c-103">UNICHAR Function</span></span>

<span data-ttu-id="2eb1c-104">返回数字的 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="2eb1c-104">Returns the Unicode character from a number.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="2eb1c-105">语法</span><span class="sxs-lookup"><span data-stu-id="2eb1c-105">Syntax</span></span>

<span data-ttu-id="2eb1c-106">UNICHAR (* **数量** *)</span><span class="sxs-lookup"><span data-stu-id="2eb1c-106">UNICHAR (** *number* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="2eb1c-107">参数</span><span class="sxs-lookup"><span data-stu-id="2eb1c-107">Parameters</span></span>

|<span data-ttu-id="2eb1c-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="2eb1c-108">**Name**</span></span>|<span data-ttu-id="2eb1c-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="2eb1c-109">**Required/Optional**</span></span>|<span data-ttu-id="2eb1c-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2eb1c-110">**Data Type**</span></span>|<span data-ttu-id="2eb1c-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="2eb1c-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2eb1c-112">_number_</span><span class="sxs-lookup"><span data-stu-id="2eb1c-112">_number_</span></span> <br/> |<span data-ttu-id="2eb1c-113">必需</span><span class="sxs-lookup"><span data-stu-id="2eb1c-113">Required</span></span>  <br/> |<span data-ttu-id="2eb1c-114">**Integer**</span><span class="sxs-lookup"><span data-stu-id="2eb1c-114">**Integer**</span></span> <br/> |<span data-ttu-id="2eb1c-115">1 到 65,535 之间（包括 1 和 65,535）的整数，若超出此范围，该函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="2eb1c-115">An integer between 1 and 65,535 (inclusive), or the function returns an error.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2eb1c-116">注解</span><span class="sxs-lookup"><span data-stu-id="2eb1c-116">Remarks</span></span>

<span data-ttu-id="2eb1c-117">生成的字符串的长度为一个 Unicode 字符（两个字符）。</span><span class="sxs-lookup"><span data-stu-id="2eb1c-117">The resulting string is one Unicode character (two characters) in length.</span></span> 
  
## <a name="example"></a><span data-ttu-id="2eb1c-118">示例</span><span class="sxs-lookup"><span data-stu-id="2eb1c-118">Example</span></span>

<span data-ttu-id="2eb1c-119">UNICHAR(65)</span><span class="sxs-lookup"><span data-stu-id="2eb1c-119">UNICHAR(65)</span></span> 
  
<span data-ttu-id="2eb1c-120">返回 A （拉丁文大写字母 A）</span><span class="sxs-lookup"><span data-stu-id="2eb1c-120">Returns A (Latin Capital Letter A)</span></span> 
  

