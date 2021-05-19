---
title: BKGPAGENAME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253219
localization_priority: Normal
ms.assetid: f6e410ef-54d5-9c08-926b-97a2a9786622
description: 以字符串形式返回背景页名称。
ms.openlocfilehash: 3b628315052117fe853c8f9c0fc36572de25d871
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410313"
---
# <a name="bkgpagename-function"></a><span data-ttu-id="eae7a-103">BKGPAGENAME 函数</span><span class="sxs-lookup"><span data-stu-id="eae7a-103">BKGPAGENAME Function</span></span>

<span data-ttu-id="eae7a-104">以字符串形式返回背景页名称。</span><span class="sxs-lookup"><span data-stu-id="eae7a-104">Returns a background page name as a string.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="eae7a-105">语法</span><span class="sxs-lookup"><span data-stu-id="eae7a-105">Syntax</span></span>

<span data-ttu-id="eae7a-106">BKGPAGENAME (\*\* *langID_opt* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="eae7a-106">BKGPAGENAME (\*\* *langID_opt* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="eae7a-107">参数</span><span class="sxs-lookup"><span data-stu-id="eae7a-107">Parameters</span></span>

|<span data-ttu-id="eae7a-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="eae7a-108">**Name**</span></span>|<span data-ttu-id="eae7a-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="eae7a-109">**Required/Optional**</span></span>|<span data-ttu-id="eae7a-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="eae7a-110">**Data Type**</span></span>|<span data-ttu-id="eae7a-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="eae7a-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="eae7a-112">_langID_opt_</span><span class="sxs-lookup"><span data-stu-id="eae7a-112">_langID_opt_</span></span> <br/> |<span data-ttu-id="eae7a-113">可选</span><span class="sxs-lookup"><span data-stu-id="eae7a-113">Optional</span></span>  <br/> |<span data-ttu-id="eae7a-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="eae7a-114">**Numeric**</span></span> <br/> |<span data-ttu-id="eae7a-p101">用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。</span><span class="sxs-lookup"><span data-stu-id="eae7a-p101">Use to specify a language for the string the function returns. Use 0 (default value) to specify the local language. Use 750 to specify universal language.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="eae7a-118">返回值</span><span class="sxs-lookup"><span data-stu-id="eae7a-118">Return value</span></span>

<span data-ttu-id="eae7a-119">String</span><span class="sxs-lookup"><span data-stu-id="eae7a-119">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="eae7a-120">备注</span><span class="sxs-lookup"><span data-stu-id="eae7a-120">Remarks</span></span>

<span data-ttu-id="eae7a-121">如果使用函数的页面没有背景页，则返回字符串" \< 无 \> 背景"。</span><span class="sxs-lookup"><span data-stu-id="eae7a-121">If the page for which you are using the function doesn't have a background page, the string "\<no background\>" is returned.</span></span> 
  
<span data-ttu-id="eae7a-122">如果传递了非法的语言代码，则将使用本地语言。</span><span class="sxs-lookup"><span data-stu-id="eae7a-122">If you pass an illegal language code, the local language is used.</span></span> 
  

