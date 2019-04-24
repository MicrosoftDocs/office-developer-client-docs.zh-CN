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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319423"
---
# <a name="name-function"></a><span data-ttu-id="5ecfd-103">NAME 函数</span><span class="sxs-lookup"><span data-stu-id="5ecfd-103">NAME Function</span></span>

<span data-ttu-id="5ecfd-104">以字符串的形式返回工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="5ecfd-104">Returns a sheet's name as a string.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5ecfd-105">语法</span><span class="sxs-lookup"><span data-stu-id="5ecfd-105">Syntax</span></span>

<span data-ttu-id="5ecfd-106">名称 (\* \* *langID_opt* \* \*)</span><span class="sxs-lookup"><span data-stu-id="5ecfd-106">NAME (\*\* *langID_opt* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="5ecfd-107">参数</span><span class="sxs-lookup"><span data-stu-id="5ecfd-107">Parameters</span></span>

|<span data-ttu-id="5ecfd-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="5ecfd-108">**Name**</span></span>|<span data-ttu-id="5ecfd-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5ecfd-109">**Required/Optional**</span></span>|<span data-ttu-id="5ecfd-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5ecfd-110">**Data Type**</span></span>|<span data-ttu-id="5ecfd-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="5ecfd-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5ecfd-112">_langID_opt_</span><span class="sxs-lookup"><span data-stu-id="5ecfd-112">_langID_opt_</span></span> <br/> |<span data-ttu-id="5ecfd-113">可选</span><span class="sxs-lookup"><span data-stu-id="5ecfd-113">Optional</span></span>  <br/> |<span data-ttu-id="5ecfd-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="5ecfd-114">**Number**</span></span> <br/> |<span data-ttu-id="5ecfd-p101">用于指定函数所返回的字符串的语言。使用 0（默认值）可以指定本地语言。使用 750 可以指定通用语言。</span><span class="sxs-lookup"><span data-stu-id="5ecfd-p101">Use to specify a language for the string the function returns. Use 0 (default value) to specify the local language. Use 750 to specify universal language.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="5ecfd-118">返回值</span><span class="sxs-lookup"><span data-stu-id="5ecfd-118">Return value</span></span>

<span data-ttu-id="5ecfd-119">字符串</span><span class="sxs-lookup"><span data-stu-id="5ecfd-119">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5ecfd-120">注解</span><span class="sxs-lookup"><span data-stu-id="5ecfd-120">Remarks</span></span>

<span data-ttu-id="5ecfd-121">如果传递了非法的语言代码，则将使用本地语言。</span><span class="sxs-lookup"><span data-stu-id="5ecfd-121">If you pass an illegal language code, the local language is used.</span></span> 
  

