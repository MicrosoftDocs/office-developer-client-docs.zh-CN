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
description: 以字符串的形式返回背景页名称。
ms.openlocfilehash: 3b628315052117fe853c8f9c0fc36572de25d871
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358539"
---
# <a name="bkgpagename-function"></a><span data-ttu-id="35666-103">BKGPAGENAME 函数</span><span class="sxs-lookup"><span data-stu-id="35666-103">BKGPAGENAME Function</span></span>

<span data-ttu-id="35666-104">以字符串的形式返回背景页名称。</span><span class="sxs-lookup"><span data-stu-id="35666-104">Returns a background page name as a string.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="35666-105">语法</span><span class="sxs-lookup"><span data-stu-id="35666-105">Syntax</span></span>

<span data-ttu-id="35666-106">BKGPAGENAME (\* \* *langID_opt* \* \*)</span><span class="sxs-lookup"><span data-stu-id="35666-106">BKGPAGENAME (\*\* *langID_opt* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="35666-107">参数</span><span class="sxs-lookup"><span data-stu-id="35666-107">Parameters</span></span>

|<span data-ttu-id="35666-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="35666-108">**Name**</span></span>|<span data-ttu-id="35666-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="35666-109">**Required/Optional**</span></span>|<span data-ttu-id="35666-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="35666-110">**Data Type**</span></span>|<span data-ttu-id="35666-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="35666-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="35666-112">_langID_opt_</span><span class="sxs-lookup"><span data-stu-id="35666-112">_langID_opt_</span></span> <br/> |<span data-ttu-id="35666-113">可选</span><span class="sxs-lookup"><span data-stu-id="35666-113">Optional</span></span>  <br/> |<span data-ttu-id="35666-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="35666-114">**Numeric**</span></span> <br/> |<span data-ttu-id="35666-p101">用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。</span><span class="sxs-lookup"><span data-stu-id="35666-p101">Use to specify a language for the string the function returns. Use 0 (default value) to specify the local language. Use 750 to specify universal language.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="35666-118">返回值</span><span class="sxs-lookup"><span data-stu-id="35666-118">Return value</span></span>

<span data-ttu-id="35666-119">字符串</span><span class="sxs-lookup"><span data-stu-id="35666-119">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="35666-120">注解</span><span class="sxs-lookup"><span data-stu-id="35666-120">Remarks</span></span>

<span data-ttu-id="35666-121">如果要对其使用该函数的页面没有背景页, 则返回字符串 "\<无背景\>"。</span><span class="sxs-lookup"><span data-stu-id="35666-121">If the page for which you are using the function doesn't have a background page, the string "\<no background\>" is returned.</span></span> 
  
<span data-ttu-id="35666-122">如果传递了非法的语言代码，则将使用本地语言。</span><span class="sxs-lookup"><span data-stu-id="35666-122">If you pass an illegal language code, the local language is used.</span></span> 
  

