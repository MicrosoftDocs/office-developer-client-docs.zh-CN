---
title: MASTERNAME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251581
localization_priority: Normal
ms.assetid: 519d79d4-9178-2231-c26d-aa7f31a43412
description: 以字符串形式返回工作表的主控名称，如果工作表没有主控板，则返回字符串"no master"。
ms.openlocfilehash: 7732cf9e8b23e2fd0fc2e3f2cc8d9ef4f39fd67f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414751"
---
# <a name="mastername-function"></a><span data-ttu-id="43fd3-103">MASTERNAME 函数</span><span class="sxs-lookup"><span data-stu-id="43fd3-103">MASTERNAME Function</span></span>

<span data-ttu-id="43fd3-104">以字符串形式返回工作表的主控名称，如果工作表没有主控板，则返回字符串"no \< \> master"。</span><span class="sxs-lookup"><span data-stu-id="43fd3-104">Returns a sheet's master name as a string, or returns the string "\<no master\>" if the sheet doesn't have a master.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="43fd3-105">语法</span><span class="sxs-lookup"><span data-stu-id="43fd3-105">Syntax</span></span>

<span data-ttu-id="43fd3-106">MASTERNAME ([ \*\* *langID_opt* \*\* ]) </span><span class="sxs-lookup"><span data-stu-id="43fd3-106">MASTERNAME ([ \*\* *langID_opt* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="43fd3-107">参数</span><span class="sxs-lookup"><span data-stu-id="43fd3-107">Parameters</span></span>

|<span data-ttu-id="43fd3-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="43fd3-108">**Name**</span></span>|<span data-ttu-id="43fd3-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="43fd3-109">**Required/Optional**</span></span>|<span data-ttu-id="43fd3-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="43fd3-110">**Data Type**</span></span>|<span data-ttu-id="43fd3-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="43fd3-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="43fd3-112">_langID_opt_</span><span class="sxs-lookup"><span data-stu-id="43fd3-112">_langID_opt_</span></span> <br/> |<span data-ttu-id="43fd3-113">可选</span><span class="sxs-lookup"><span data-stu-id="43fd3-113">Optional</span></span>  <br/> |<span data-ttu-id="43fd3-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="43fd3-114">**Number**</span></span> <br/> |<span data-ttu-id="43fd3-p101">用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。</span><span class="sxs-lookup"><span data-stu-id="43fd3-p101">Use to specify a language for the string the function returns. Use 0 (default value) to specify the local language. Use 750 to specify universal language.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="43fd3-118">返回值</span><span class="sxs-lookup"><span data-stu-id="43fd3-118">Return value</span></span>

<span data-ttu-id="43fd3-119">String</span><span class="sxs-lookup"><span data-stu-id="43fd3-119">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="43fd3-120">备注</span><span class="sxs-lookup"><span data-stu-id="43fd3-120">Remarks</span></span>

<span data-ttu-id="43fd3-121">如果传递了非法的语言代码，则将使用本地语言。</span><span class="sxs-lookup"><span data-stu-id="43fd3-121">If you pass an illegal language code, the local language is used.</span></span> 
  

