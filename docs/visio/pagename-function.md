---
title: PAGENAME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251577
localization_priority: Normal
ms.assetid: 12e45f46-e773-9445-4c7f-c726ab648671
description: 以字符串的形式返回页面名称。
ms.openlocfilehash: d5527bde58a68c96bd75773f3a0a8c30f64fa20d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438650"
---
# <a name="pagename-function"></a><span data-ttu-id="c141b-103">PAGENAME 函数</span><span class="sxs-lookup"><span data-stu-id="c141b-103">PAGENAME Function</span></span>

<span data-ttu-id="c141b-104">以字符串的形式返回页面名称。</span><span class="sxs-lookup"><span data-stu-id="c141b-104">Returns the page name as a string.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c141b-105">语法</span><span class="sxs-lookup"><span data-stu-id="c141b-105">Syntax</span></span>

<span data-ttu-id="c141b-106">PAGENAME (\* \* *langID_opt* \* \*)</span><span class="sxs-lookup"><span data-stu-id="c141b-106">PAGENAME (\*\* *langID_opt* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c141b-107">参数</span><span class="sxs-lookup"><span data-stu-id="c141b-107">Parameters</span></span>

|<span data-ttu-id="c141b-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="c141b-108">**Name**</span></span>|<span data-ttu-id="c141b-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c141b-109">**Required/Optional**</span></span>|<span data-ttu-id="c141b-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c141b-110">**Data Type**</span></span>|<span data-ttu-id="c141b-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="c141b-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c141b-112">_langID_opt_</span><span class="sxs-lookup"><span data-stu-id="c141b-112">_langID_opt_</span></span> <br/> |<span data-ttu-id="c141b-113">可选</span><span class="sxs-lookup"><span data-stu-id="c141b-113">Optional</span></span>  <br/> |<span data-ttu-id="c141b-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="c141b-114">**Number**</span></span> <br/> |<span data-ttu-id="c141b-p101">用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。</span><span class="sxs-lookup"><span data-stu-id="c141b-p101">Use to specify a language for the string the function returns. Use 0 (default value) to specify the local language. Use 750 to specify universal language.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="c141b-118">返回值</span><span class="sxs-lookup"><span data-stu-id="c141b-118">Return value</span></span>

<span data-ttu-id="c141b-119">String</span><span class="sxs-lookup"><span data-stu-id="c141b-119">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c141b-120">说明</span><span class="sxs-lookup"><span data-stu-id="c141b-120">Remarks</span></span>

<span data-ttu-id="c141b-121">如果传递了非法的语言代码，则将使用本地语言。</span><span class="sxs-lookup"><span data-stu-id="c141b-121">If you pass an illegal language code, the local language is used.</span></span>
  

