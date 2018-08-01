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
description: 将转换公式生成 16 位字符代码的扩大的单字节还是多字节字符集代码，为 16 位 Unicode 字符代码，使用指定的字符集的字符串。
ms.openlocfilehash: 66dc3e801585077a9521cd93f8ae78c47f8a746b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781108"
---
# <a name="rewiden-function"></a><span data-ttu-id="ea3a3-103">REWIDEN 函数</span><span class="sxs-lookup"><span data-stu-id="ea3a3-103">REWIDEN Function</span></span>

<span data-ttu-id="ea3a3-104">将转换公式生成 16 位字符代码的扩大的单字节还是多字节字符集代码，为 16 位 Unicode 字符代码，使用指定的字符集的字符串。</span><span class="sxs-lookup"><span data-stu-id="ea3a3-104">Converts a formula that produces 16-bit character codes that are widened single-byte or multibyte character-set codes into a string of 16-bit Unicode character codes, using the specified character sets.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="ea3a3-105">语法</span><span class="sxs-lookup"><span data-stu-id="ea3a3-105">Syntax</span></span>

<span data-ttu-id="ea3a3-106">REWIDEN (* * *srcCharSet* * *，* * *dstCharSet* * *，* **文本** *)</span><span class="sxs-lookup"><span data-stu-id="ea3a3-106">REWIDEN(** *srcCharSet* **, ** *dstCharSet* **, ** *text* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="ea3a3-107">参数</span><span class="sxs-lookup"><span data-stu-id="ea3a3-107">Parameters</span></span>

|<span data-ttu-id="ea3a3-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="ea3a3-108">**Name**</span></span>|<span data-ttu-id="ea3a3-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="ea3a3-109">**Required/Optional**</span></span>|<span data-ttu-id="ea3a3-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ea3a3-110">**Data Type**</span></span>|<span data-ttu-id="ea3a3-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="ea3a3-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ea3a3-112">_srcCharSet_</span><span class="sxs-lookup"><span data-stu-id="ea3a3-112">_srcCharSet_</span></span> <br/> |<span data-ttu-id="ea3a3-113">必需</span><span class="sxs-lookup"><span data-stu-id="ea3a3-113">Required</span></span>  <br/> |<span data-ttu-id="ea3a3-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="ea3a3-114">**String**</span></span> <br/> |<span data-ttu-id="ea3a3-115">源文档中的字符集。</span><span class="sxs-lookup"><span data-stu-id="ea3a3-115">The character set in the source document.</span></span>  <br/> |
| <span data-ttu-id="ea3a3-116">_dstCharSet_</span><span class="sxs-lookup"><span data-stu-id="ea3a3-116">_dstCharSet_</span></span> <br/> |<span data-ttu-id="ea3a3-117">必需</span><span class="sxs-lookup"><span data-stu-id="ea3a3-117">Required</span></span>  <br/> |<span data-ttu-id="ea3a3-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="ea3a3-118">**String**</span></span> <br/> | <span data-ttu-id="ea3a3-119">目标文档中的字符集。</span><span class="sxs-lookup"><span data-stu-id="ea3a3-119">The character set in the destination document.</span></span>  <br/> |
| <span data-ttu-id="ea3a3-120">_text_</span><span class="sxs-lookup"><span data-stu-id="ea3a3-120">_text_</span></span> <br/> |<span data-ttu-id="ea3a3-121">必需</span><span class="sxs-lookup"><span data-stu-id="ea3a3-121">Required</span></span>  <br/> |<span data-ttu-id="ea3a3-122">**字符串**</span><span class="sxs-lookup"><span data-stu-id="ea3a3-122">**String**</span></span> <br/> |<span data-ttu-id="ea3a3-123">要转换的文本。</span><span class="sxs-lookup"><span data-stu-id="ea3a3-123">The text to convert.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ea3a3-124">注解</span><span class="sxs-lookup"><span data-stu-id="ea3a3-124">Remarks</span></span>

<span data-ttu-id="ea3a3-p101">REWIDEN 函数用于从 Visio 2002 文档到 Visio 2003 文档的自动转换。不建议将该函数用于其他方面。</span><span class="sxs-lookup"><span data-stu-id="ea3a3-p101">The REWIDEN function is used in automatic conversion of Visio 2002 documents to Visio 2003 documents. Other use is not recommended.</span></span>
  

