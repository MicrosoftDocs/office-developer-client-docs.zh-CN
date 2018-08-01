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
description: 作为字符串返回页名称。
ms.openlocfilehash: 530707530d60955f460d6a747024b98ebdd5ab62
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780836"
---
# <a name="pagename-function"></a><span data-ttu-id="4931a-103">PAGENAME 函数</span><span class="sxs-lookup"><span data-stu-id="4931a-103">PAGENAME Function</span></span>

<span data-ttu-id="4931a-104">作为字符串返回页名称。</span><span class="sxs-lookup"><span data-stu-id="4931a-104">Returns the page name as a string.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="4931a-105">语法</span><span class="sxs-lookup"><span data-stu-id="4931a-105">Syntax</span></span>

<span data-ttu-id="4931a-106">PAGENAME (* * *langID_opt* * *)</span><span class="sxs-lookup"><span data-stu-id="4931a-106">PAGENAME (** *langID_opt* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="4931a-107">参数</span><span class="sxs-lookup"><span data-stu-id="4931a-107">Parameters</span></span>

|<span data-ttu-id="4931a-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="4931a-108">**Name**</span></span>|<span data-ttu-id="4931a-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="4931a-109">**Required/Optional**</span></span>|<span data-ttu-id="4931a-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4931a-110">**Data Type**</span></span>|<span data-ttu-id="4931a-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="4931a-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4931a-112">_langID_opt_</span><span class="sxs-lookup"><span data-stu-id="4931a-112">_langID_opt_</span></span> <br/> |<span data-ttu-id="4931a-113">可选</span><span class="sxs-lookup"><span data-stu-id="4931a-113">Optional</span></span>  <br/> |<span data-ttu-id="4931a-114">**编号**</span><span class="sxs-lookup"><span data-stu-id="4931a-114">**Number**</span></span> <br/> |<span data-ttu-id="4931a-p101">用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。</span><span class="sxs-lookup"><span data-stu-id="4931a-p101">Use to specify a language for the string the function returns. Use 0 (default value) to specify the local language. Use 750 to specify universal language.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="4931a-118">返回值</span><span class="sxs-lookup"><span data-stu-id="4931a-118">Return value</span></span>

<span data-ttu-id="4931a-119">字符串</span><span class="sxs-lookup"><span data-stu-id="4931a-119">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4931a-120">注解</span><span class="sxs-lookup"><span data-stu-id="4931a-120">Remarks</span></span>

<span data-ttu-id="4931a-121">如果传递了非法的语言代码，则将使用本地语言。</span><span class="sxs-lookup"><span data-stu-id="4931a-121">If you pass an illegal language code, the local language is used.</span></span>
  

