---
title: REPLACE 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60108
localization_priority: Normal
ms.assetid: 70c9fc1d-6e7b-479f-effd-0d4bc8ae0f72
description: 根据指定的字符数，将文本字符串的部分用其他文本字符串替换。
ms.openlocfilehash: 75a156d720ca276e75fccf932124ae905e4350b0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414352"
---
# <a name="replace-function-visioshapesheet"></a><span data-ttu-id="912b9-103">REPLACE 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="912b9-103">REPLACE Function (VisioShapeSheet)</span></span>

<span data-ttu-id="912b9-104">根据指定的字符数，将文本字符串的部分用其他文本字符串替换。</span><span class="sxs-lookup"><span data-stu-id="912b9-104">Replaces part of a text string, based on the number of characters you specify, with a different text string.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="912b9-105">语法</span><span class="sxs-lookup"><span data-stu-id="912b9-105">Syntax</span></span>

<span data-ttu-id="912b9-106">REPLACE (\*\* *old_text* \*\*， \*\* *start_num* \*\*， \*\* *num_chars* \*\*， \*\* *new_text* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="912b9-106">REPLACE (\*\* *old_text* \*\*, \*\* *start_num* \*\*, \*\* *num_chars* \*\*, \*\* *new_text* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="912b9-107">参数</span><span class="sxs-lookup"><span data-stu-id="912b9-107">Parameters</span></span>

|<span data-ttu-id="912b9-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="912b9-108">**Name**</span></span>|<span data-ttu-id="912b9-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="912b9-109">**Required/Optional**</span></span>|<span data-ttu-id="912b9-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="912b9-110">**Data Type**</span></span>|<span data-ttu-id="912b9-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="912b9-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="912b9-112">_old_text_</span><span class="sxs-lookup"><span data-stu-id="912b9-112">_old_text_</span></span> <br/> |<span data-ttu-id="912b9-113">必需</span><span class="sxs-lookup"><span data-stu-id="912b9-113">Required</span></span>  <br/> |<span data-ttu-id="912b9-114">**String**</span><span class="sxs-lookup"><span data-stu-id="912b9-114">**String**</span></span> <br/> |<span data-ttu-id="912b9-115">要替换其中的一些字符的文本。</span><span class="sxs-lookup"><span data-stu-id="912b9-115">The text in which you want to replace some characters.</span></span>  <br/> |
| <span data-ttu-id="912b9-116">_start_num_</span><span class="sxs-lookup"><span data-stu-id="912b9-116">_start_num_</span></span> <br/> |<span data-ttu-id="912b9-117">必需</span><span class="sxs-lookup"><span data-stu-id="912b9-117">Required</span></span>  <br/> |<span data-ttu-id="912b9-118">**Number**</span><span class="sxs-lookup"><span data-stu-id="912b9-118">**Number**</span></span> <br/> |<span data-ttu-id="912b9-119">字符在要替换为 _old_text_ 中 _的位置new_text。_</span><span class="sxs-lookup"><span data-stu-id="912b9-119">The position of the character in  _old_text_ that you want to replace with  _new_text_.</span></span> <span data-ttu-id="912b9-120">字符串中的第一个字符处于位置 1。</span><span class="sxs-lookup"><span data-stu-id="912b9-120">The first character in the string is position 1.</span></span>  <br/> |
| <span data-ttu-id="912b9-121">_num_chars_</span><span class="sxs-lookup"><span data-stu-id="912b9-121">_num_chars_</span></span> <br/> |<span data-ttu-id="912b9-122">必需</span><span class="sxs-lookup"><span data-stu-id="912b9-122">Required</span></span>  <br/> |<span data-ttu-id="912b9-123">**Number**</span><span class="sxs-lookup"><span data-stu-id="912b9-123">**Number**</span></span> <br/> |<span data-ttu-id="912b9-124">要  _替换old_text中的_ 字符数</span><span class="sxs-lookup"><span data-stu-id="912b9-124">The number of characters in  _old_text_ that you want to replace</span></span>  <br/> |
| <span data-ttu-id="912b9-125">_new_text_</span><span class="sxs-lookup"><span data-stu-id="912b9-125">_new_text_</span></span> <br/> |<span data-ttu-id="912b9-126">必需</span><span class="sxs-lookup"><span data-stu-id="912b9-126">Required</span></span>  <br/> |<span data-ttu-id="912b9-127">**String**</span><span class="sxs-lookup"><span data-stu-id="912b9-127">**String**</span></span> <br/> |<span data-ttu-id="912b9-128">将替换中  _字符的文本_ old_text。</span><span class="sxs-lookup"><span data-stu-id="912b9-128">The text that will replace characters in  _old_text_.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="912b9-129">返回值</span><span class="sxs-lookup"><span data-stu-id="912b9-129">Return value</span></span>

<span data-ttu-id="912b9-130">字符串</span><span class="sxs-lookup"><span data-stu-id="912b9-130">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="912b9-131">备注</span><span class="sxs-lookup"><span data-stu-id="912b9-131">Remarks</span></span>

<span data-ttu-id="912b9-p102">要替换出现在文本字符串中的特定位置的文本时，请使用 REPLACE 函数。如果想要替换文本字符串中的特定文本，则请使用 SUBSTITUTE 函数。</span><span class="sxs-lookup"><span data-stu-id="912b9-p102">Use the REPLACE function when you want to replace text that occurs in a specific location in a text string. If you want to replace specific text in a text string, use the SUBSTITUTE function.</span></span>
  
## <a name="example"></a><span data-ttu-id="912b9-134">示例</span><span class="sxs-lookup"><span data-stu-id="912b9-134">Example</span></span>

<span data-ttu-id="912b9-135">REPLACE ("01/03/2002",9,2,"03")</span><span class="sxs-lookup"><span data-stu-id="912b9-135">REPLACE ("01/03/2002",9,2,"03")</span></span> 
  
<span data-ttu-id="912b9-136">返回 01/03/2003。</span><span class="sxs-lookup"><span data-stu-id="912b9-136">Returns 01/03/2003.</span></span> 
  

