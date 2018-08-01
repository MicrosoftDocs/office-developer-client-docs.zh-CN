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
description: 作为字符串返回工作表的名称。
ms.openlocfilehash: 0d3a70573177d8e16a16972d0a08245381b209dd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780783"
---
# <a name="name-function"></a><span data-ttu-id="5c21f-103">NAME 函数</span><span class="sxs-lookup"><span data-stu-id="5c21f-103">NAME Function</span></span>

<span data-ttu-id="5c21f-104">作为字符串返回工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="5c21f-104">Returns a sheet's name as a string.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5c21f-105">语法</span><span class="sxs-lookup"><span data-stu-id="5c21f-105">Syntax</span></span>

<span data-ttu-id="5c21f-106">名称 (* * *langID_opt* * *)</span><span class="sxs-lookup"><span data-stu-id="5c21f-106">NAME (** *langID_opt* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="5c21f-107">参数</span><span class="sxs-lookup"><span data-stu-id="5c21f-107">Parameters</span></span>

|<span data-ttu-id="5c21f-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="5c21f-108">**Name**</span></span>|<span data-ttu-id="5c21f-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5c21f-109">**Required/Optional**</span></span>|<span data-ttu-id="5c21f-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5c21f-110">**Data Type**</span></span>|<span data-ttu-id="5c21f-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c21f-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5c21f-112">_langID_opt_</span><span class="sxs-lookup"><span data-stu-id="5c21f-112">_langID_opt_</span></span> <br/> |<span data-ttu-id="5c21f-113">可选</span><span class="sxs-lookup"><span data-stu-id="5c21f-113">Optional</span></span>  <br/> |<span data-ttu-id="5c21f-114">**编号**</span><span class="sxs-lookup"><span data-stu-id="5c21f-114">**Number**</span></span> <br/> |<span data-ttu-id="5c21f-p101">用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。</span><span class="sxs-lookup"><span data-stu-id="5c21f-p101">Use to specify a language for the string the function returns. Use 0 (default value) to specify the local language. Use 750 to specify universal language.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="5c21f-118">返回值</span><span class="sxs-lookup"><span data-stu-id="5c21f-118">Return value</span></span>

<span data-ttu-id="5c21f-119">字符串</span><span class="sxs-lookup"><span data-stu-id="5c21f-119">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5c21f-120">注解</span><span class="sxs-lookup"><span data-stu-id="5c21f-120">Remarks</span></span>

<span data-ttu-id="5c21f-121">如果传递了非法的语言代码，则将使用本地语言。</span><span class="sxs-lookup"><span data-stu-id="5c21f-121">If you pass an illegal language code, the local language is used.</span></span> 
  

