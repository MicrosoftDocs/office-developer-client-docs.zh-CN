---
title: TRIM 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027318
localization_priority: Normal
ms.assetid: 6f2d84fd-27eb-4c2f-a2e1-43d20e0c78be
description: 删除文本中的所有空格，单词之间的单个空格除外。
ms.openlocfilehash: b396572041e880451ceb1ec6f0508528c0807bfc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781565"
---
# <a name="trim-function"></a><span data-ttu-id="cf714-103">TRIM 函数</span><span class="sxs-lookup"><span data-stu-id="cf714-103">TRIM Function</span></span>

<span data-ttu-id="cf714-104">删除文本中的所有空格，单词之间的单个空格除外。</span><span class="sxs-lookup"><span data-stu-id="cf714-104">Removes all space from text, except for single spaces between words.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="cf714-105">语法</span><span class="sxs-lookup"><span data-stu-id="cf714-105">Syntax</span></span>

<span data-ttu-id="cf714-106">修整 (* **文本** *)</span><span class="sxs-lookup"><span data-stu-id="cf714-106">TRIM (** *text* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="cf714-107">参数</span><span class="sxs-lookup"><span data-stu-id="cf714-107">Parameters</span></span>

|<span data-ttu-id="cf714-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="cf714-108">**Name**</span></span>|<span data-ttu-id="cf714-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="cf714-109">**Required/Optional**</span></span>|<span data-ttu-id="cf714-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cf714-110">**Data Type**</span></span>|<span data-ttu-id="cf714-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="cf714-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="cf714-112">_text_</span><span class="sxs-lookup"><span data-stu-id="cf714-112">_text_</span></span> <br/> |<span data-ttu-id="cf714-113">必需</span><span class="sxs-lookup"><span data-stu-id="cf714-113">Required</span></span>  <br/> |<span data-ttu-id="cf714-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="cf714-114">**String**</span></span> <br/> |<span data-ttu-id="cf714-115">要从中删除空格的文本。</span><span class="sxs-lookup"><span data-stu-id="cf714-115">The text from which you want to remove spaces.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="cf714-116">返回值</span><span class="sxs-lookup"><span data-stu-id="cf714-116">Return value</span></span>

<span data-ttu-id="cf714-117">String</span><span class="sxs-lookup"><span data-stu-id="cf714-117">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="cf714-118">注解</span><span class="sxs-lookup"><span data-stu-id="cf714-118">Remarks</span></span>

<span data-ttu-id="cf714-119">可以对从另一个应用程序接收的、可能包含不规则空格的文本使用 TRIM 函数。</span><span class="sxs-lookup"><span data-stu-id="cf714-119">You can use the TRIM function on text that you have received from another application that may have irregular spacing.</span></span>
  
## <a name="example"></a><span data-ttu-id="cf714-120">示例</span><span class="sxs-lookup"><span data-stu-id="cf714-120">Example</span></span>

<span data-ttu-id="cf714-121">TRIM ("January 1, 2003 ")</span><span class="sxs-lookup"><span data-stu-id="cf714-121">TRIM ("January 1, 2003 ")</span></span> 
  
<span data-ttu-id="cf714-122">返回“January 1, 2003”。</span><span class="sxs-lookup"><span data-stu-id="cf714-122">Returns "January 1, 2003".</span></span> 
  

