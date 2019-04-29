---
title: NAME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251580
localization_priority: Normal
ms.assetid: 1ca67a09-9df2-37f5-b269-e761d76bb011
description: 以字符串的形式返回工作表的名称。
ms.openlocfilehash: 7d0a4e9f3c5f70be07e9cc5691f52afcbc7bea68
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416795"
---
# <a name="name-function"></a><span data-ttu-id="b6d04-103">NAME 函数</span><span class="sxs-lookup"><span data-stu-id="b6d04-103">NAME Function</span></span>

<span data-ttu-id="b6d04-104">以字符串的形式返回工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="b6d04-104">Returns a sheet's name as a string.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="b6d04-105">语法</span><span class="sxs-lookup"><span data-stu-id="b6d04-105">Syntax</span></span>

<span data-ttu-id="b6d04-106">名称 (\* \* *langID_opt* \* \*)</span><span class="sxs-lookup"><span data-stu-id="b6d04-106">NAME (\*\* *langID_opt* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="b6d04-107">参数</span><span class="sxs-lookup"><span data-stu-id="b6d04-107">Parameters</span></span>

|<span data-ttu-id="b6d04-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="b6d04-108">**Name**</span></span>|<span data-ttu-id="b6d04-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="b6d04-109">**Required/Optional**</span></span>|<span data-ttu-id="b6d04-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b6d04-110">**Data Type**</span></span>|<span data-ttu-id="b6d04-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="b6d04-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b6d04-112">_langID_opt_</span><span class="sxs-lookup"><span data-stu-id="b6d04-112">_langID_opt_</span></span> <br/> |<span data-ttu-id="b6d04-113">可选</span><span class="sxs-lookup"><span data-stu-id="b6d04-113">Optional</span></span>  <br/> |<span data-ttu-id="b6d04-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="b6d04-114">**Number**</span></span> <br/> |<span data-ttu-id="b6d04-p101">用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。</span><span class="sxs-lookup"><span data-stu-id="b6d04-p101">Use to specify a language for the string the function returns. Use 0 (default value) to specify the local language. Use 750 to specify universal language.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="b6d04-118">返回值</span><span class="sxs-lookup"><span data-stu-id="b6d04-118">Return value</span></span>

<span data-ttu-id="b6d04-119">String</span><span class="sxs-lookup"><span data-stu-id="b6d04-119">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b6d04-120">说明</span><span class="sxs-lookup"><span data-stu-id="b6d04-120">Remarks</span></span>

<span data-ttu-id="b6d04-121">如果传递了非法的语言代码，则将使用本地语言。</span><span class="sxs-lookup"><span data-stu-id="b6d04-121">If you pass an illegal language code, the local language is used.</span></span> 
  

