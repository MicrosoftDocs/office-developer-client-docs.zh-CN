---
title: LEFT 的函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1021757
localization_priority: Normal
ms.assetid: 0c2f6e06-b772-2006-ec7b-8695d097f146
description: 文本字符串，根据您指定的字符数中返回的最左侧的字符。
ms.openlocfilehash: 4e8deb3098ce6d217dcce0cae23d07ed723d9fb8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780555"
---
# <a name="left-function-visioshapesheet"></a><span data-ttu-id="d85c2-103">LEFT 的函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="d85c2-103">LEFT Function (VisioShapeSheet)</span></span>

<span data-ttu-id="d85c2-104">文本字符串，根据您指定的字符数中返回的最左侧的字符。</span><span class="sxs-lookup"><span data-stu-id="d85c2-104">Returns the left-most character or characters in a text string, based on the number of characters you specify.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="d85c2-105">语法</span><span class="sxs-lookup"><span data-stu-id="d85c2-105">Syntax</span></span>

<span data-ttu-id="d85c2-106">左 (* **文本** *，[，* * *num_chars_opt* * *])</span><span class="sxs-lookup"><span data-stu-id="d85c2-106">LEFT(** *text* **, [, ** *num_chars_opt* ** ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d85c2-107">参数</span><span class="sxs-lookup"><span data-stu-id="d85c2-107">Parameters</span></span>

|<span data-ttu-id="d85c2-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="d85c2-108">**Name**</span></span>|<span data-ttu-id="d85c2-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d85c2-109">**Required/Optional**</span></span>|<span data-ttu-id="d85c2-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d85c2-110">**Data Type**</span></span>|<span data-ttu-id="d85c2-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d85c2-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d85c2-112">_text_</span><span class="sxs-lookup"><span data-stu-id="d85c2-112">_text_</span></span> <br/> |<span data-ttu-id="d85c2-113">必需</span><span class="sxs-lookup"><span data-stu-id="d85c2-113">Required</span></span>  <br/> |<span data-ttu-id="d85c2-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="d85c2-114">**String**</span></span> <br/> |<span data-ttu-id="d85c2-115">包含要提取的字符的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="d85c2-115">The text string that contains the characters you want to extract.</span></span>  <br/> |
| <span data-ttu-id="d85c2-116">_num_chars_opt_</span><span class="sxs-lookup"><span data-stu-id="d85c2-116">_num_chars_opt_</span></span> <br/> |<span data-ttu-id="d85c2-117">可选</span><span class="sxs-lookup"><span data-stu-id="d85c2-117">Optional</span></span>  <br/> |<span data-ttu-id="d85c2-118">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="d85c2-118">**Numeric**</span></span> <br/> |<span data-ttu-id="d85c2-119">要提取的字符数。</span><span class="sxs-lookup"><span data-stu-id="d85c2-119">The number of characters you want to extract.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="d85c2-120">返回值</span><span class="sxs-lookup"><span data-stu-id="d85c2-120">Return value</span></span>

<span data-ttu-id="d85c2-121">字符串</span><span class="sxs-lookup"><span data-stu-id="d85c2-121">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d85c2-122">说明</span><span class="sxs-lookup"><span data-stu-id="d85c2-122">Remarks</span></span>

<span data-ttu-id="d85c2-123">_Num_chars_opt_的值必须大于或等于零 (0)。</span><span class="sxs-lookup"><span data-stu-id="d85c2-123">The value of  _num_chars_opt_ must be greater than or equal to zero (0).</span></span> 
  
<span data-ttu-id="d85c2-124">如果_num_chars_opt_大于 text 的长度，LEFT 返回的所有文本。</span><span class="sxs-lookup"><span data-stu-id="d85c2-124">If  _num_chars_opt_ is greater than the length of the text, LEFT returns all of the text.</span></span> <span data-ttu-id="d85c2-125">如果省略_num_chars_opt_ ，则假定为 1。</span><span class="sxs-lookup"><span data-stu-id="d85c2-125">If  _num_chars_opt_ is omitted, it is assumed to be 1.</span></span> 
  
## <a name="example"></a><span data-ttu-id="d85c2-126">示例</span><span class="sxs-lookup"><span data-stu-id="d85c2-126">Example</span></span>

<span data-ttu-id="d85c2-127">LEFT ("January 1, 2004", 3)</span><span class="sxs-lookup"><span data-stu-id="d85c2-127">LEFT ("January 1, 2004", 3)</span></span> 
  
<span data-ttu-id="d85c2-128">返回值“Jan”。</span><span class="sxs-lookup"><span data-stu-id="d85c2-128">Returns the value "Jan".</span></span> 
  

