---
title: REWIDEN 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033808
localization_priority: Normal
ms.assetid: c20842cd-86b1-83fa-49ba-118936013b6f
description: 使用指定的字符集将生成的16位字符代码的公式转换为16位 Unicode 字符代码的字符串, 这些字符是由16位 Unicode 字符代码组成的字符串。
ms.openlocfilehash: c885487f91e541027b7ba09812e7321a9deb00ac
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326766"
---
# <a name="rewiden-function"></a><span data-ttu-id="2dfe7-103">REWIDEN 函数</span><span class="sxs-lookup"><span data-stu-id="2dfe7-103">REWIDEN Function</span></span>

<span data-ttu-id="2dfe7-104">使用指定的字符集将生成的16位字符代码的公式转换为16位 Unicode 字符代码的字符串, 这些字符是由16位 Unicode 字符代码组成的字符串。</span><span class="sxs-lookup"><span data-stu-id="2dfe7-104">Converts a formula that produces 16-bit character codes that are widened single-byte or multibyte character-set codes into a string of 16-bit Unicode character codes, using the specified character sets.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="2dfe7-105">语法</span><span class="sxs-lookup"><span data-stu-id="2dfe7-105">Syntax</span></span>

<span data-ttu-id="2dfe7-106">REWIDEN (\* \* *srcCharSet* \* \*, \* \* *dstCharSet* \* \*, \* \* *text* \* \*)</span><span class="sxs-lookup"><span data-stu-id="2dfe7-106">REWIDEN(\*\* *srcCharSet* \*\*, \*\* *dstCharSet* \*\*, \*\* *text* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="2dfe7-107">参数</span><span class="sxs-lookup"><span data-stu-id="2dfe7-107">Parameters</span></span>

|<span data-ttu-id="2dfe7-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="2dfe7-108">**Name**</span></span>|<span data-ttu-id="2dfe7-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="2dfe7-109">**Required/Optional**</span></span>|<span data-ttu-id="2dfe7-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2dfe7-110">**Data Type**</span></span>|<span data-ttu-id="2dfe7-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="2dfe7-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2dfe7-112">_srcCharSet_</span><span class="sxs-lookup"><span data-stu-id="2dfe7-112">_srcCharSet_</span></span> <br/> |<span data-ttu-id="2dfe7-113">必需</span><span class="sxs-lookup"><span data-stu-id="2dfe7-113">Required</span></span>  <br/> |<span data-ttu-id="2dfe7-114">**String**</span><span class="sxs-lookup"><span data-stu-id="2dfe7-114">**String**</span></span> <br/> |<span data-ttu-id="2dfe7-115">源文档中的字符集。</span><span class="sxs-lookup"><span data-stu-id="2dfe7-115">The character set in the source document.</span></span>  <br/> |
| <span data-ttu-id="2dfe7-116">_dstCharSet_</span><span class="sxs-lookup"><span data-stu-id="2dfe7-116">_dstCharSet_</span></span> <br/> |<span data-ttu-id="2dfe7-117">必需</span><span class="sxs-lookup"><span data-stu-id="2dfe7-117">Required</span></span>  <br/> |<span data-ttu-id="2dfe7-118">**String**</span><span class="sxs-lookup"><span data-stu-id="2dfe7-118">**String**</span></span> <br/> | <span data-ttu-id="2dfe7-119">目标文档中的字符集。</span><span class="sxs-lookup"><span data-stu-id="2dfe7-119">The character set in the destination document.</span></span>  <br/> |
| <span data-ttu-id="2dfe7-120">_text_</span><span class="sxs-lookup"><span data-stu-id="2dfe7-120">_text_</span></span> <br/> |<span data-ttu-id="2dfe7-121">必需</span><span class="sxs-lookup"><span data-stu-id="2dfe7-121">Required</span></span>  <br/> |<span data-ttu-id="2dfe7-122">**String**</span><span class="sxs-lookup"><span data-stu-id="2dfe7-122">**String**</span></span> <br/> |<span data-ttu-id="2dfe7-123">要转换的文本。</span><span class="sxs-lookup"><span data-stu-id="2dfe7-123">The text to convert.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2dfe7-124">注解</span><span class="sxs-lookup"><span data-stu-id="2dfe7-124">Remarks</span></span>

<span data-ttu-id="2dfe7-p101">REWIDEN 函数用于从 Visio 2002 文档到 Visio 2003 文档的自动转换。不建议将该函数用于其他方面。</span><span class="sxs-lookup"><span data-stu-id="2dfe7-p101">The REWIDEN function is used in automatic conversion of Visio 2002 documents to Visio 2003 documents. Other use is not recommended.</span></span>
  

