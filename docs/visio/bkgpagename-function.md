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
description: 作为字符串返回背景页名称。
ms.openlocfilehash: 290fa62242298b3c513bf2870df37204fab31bf3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779774"
---
# <a name="bkgpagename-function"></a><span data-ttu-id="4ebb9-103">BKGPAGENAME 函数</span><span class="sxs-lookup"><span data-stu-id="4ebb9-103">BKGPAGENAME Function</span></span>

<span data-ttu-id="4ebb9-104">作为字符串返回背景页名称。</span><span class="sxs-lookup"><span data-stu-id="4ebb9-104">Returns a background page name as a string.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="4ebb9-105">语法</span><span class="sxs-lookup"><span data-stu-id="4ebb9-105">Syntax</span></span>

<span data-ttu-id="4ebb9-106">BKGPAGENAME (* * *langID_opt* * *)</span><span class="sxs-lookup"><span data-stu-id="4ebb9-106">BKGPAGENAME (** *langID_opt* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="4ebb9-107">参数</span><span class="sxs-lookup"><span data-stu-id="4ebb9-107">Parameters</span></span>

|<span data-ttu-id="4ebb9-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="4ebb9-108">**Name**</span></span>|<span data-ttu-id="4ebb9-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="4ebb9-109">**Required/Optional**</span></span>|<span data-ttu-id="4ebb9-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4ebb9-110">**Data Type**</span></span>|<span data-ttu-id="4ebb9-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="4ebb9-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4ebb9-112">_langID_opt_</span><span class="sxs-lookup"><span data-stu-id="4ebb9-112">_langID_opt_</span></span> <br/> |<span data-ttu-id="4ebb9-113">可选</span><span class="sxs-lookup"><span data-stu-id="4ebb9-113">Optional</span></span>  <br/> |<span data-ttu-id="4ebb9-114">**数字**</span><span class="sxs-lookup"><span data-stu-id="4ebb9-114">**Numeric**</span></span> <br/> |<span data-ttu-id="4ebb9-p101">用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。</span><span class="sxs-lookup"><span data-stu-id="4ebb9-p101">Use to specify a language for the string the function returns. Use 0 (default value) to specify the local language. Use 750 to specify universal language.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="4ebb9-118">返回值</span><span class="sxs-lookup"><span data-stu-id="4ebb9-118">Return value</span></span>

<span data-ttu-id="4ebb9-119">String</span><span class="sxs-lookup"><span data-stu-id="4ebb9-119">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4ebb9-120">注解</span><span class="sxs-lookup"><span data-stu-id="4ebb9-120">Remarks</span></span>

<span data-ttu-id="4ebb9-121">如果使用该函数页上不具有背景页，该字符串"\<没有背景\>"返回。</span><span class="sxs-lookup"><span data-stu-id="4ebb9-121">If the page for which you are using the function doesn't have a background page, the string "\<no background\>" is returned.</span></span> 
  
<span data-ttu-id="4ebb9-122">如果传递了非法的语言代码，则将使用本地语言。</span><span class="sxs-lookup"><span data-stu-id="4ebb9-122">If you pass an illegal language code, the local language is used.</span></span> 
  

