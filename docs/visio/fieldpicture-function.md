---
title: FIELDPICTURE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251592
localization_priority: Normal
ms.assetid: df88c55f-c098-dd4c-bf53-c7d7b60cf719
description: 返回与 Microsoft Visio 内部文本域格式代码匹配的格式图片字符串。
ms.openlocfilehash: 1ab24c602c7975cf6be22a564a8b9ee9aa0d6f46
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322545"
---
# <a name="fieldpicture-function"></a><span data-ttu-id="93a9d-103">FIELDPICTURE 函数</span><span class="sxs-lookup"><span data-stu-id="93a9d-103">FIELDPICTURE Function</span></span>

<span data-ttu-id="93a9d-104">返回与 Microsoft Visio 内部文本域格式代码匹配的格式图片字符串。</span><span class="sxs-lookup"><span data-stu-id="93a9d-104">Returns a format-picture string that matches the Microsoft Visio internal text field format code.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="93a9d-105">语法</span><span class="sxs-lookup"><span data-stu-id="93a9d-105">Syntax</span></span>

<span data-ttu-id="93a9d-106">FIELDPICTURE (\* **代码** \*)</span><span class="sxs-lookup"><span data-stu-id="93a9d-106">FIELDPICTURE(\*\* *code* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="93a9d-107">参数</span><span class="sxs-lookup"><span data-stu-id="93a9d-107">Parameters</span></span>

|<span data-ttu-id="93a9d-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="93a9d-108">**Name**</span></span>|<span data-ttu-id="93a9d-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="93a9d-109">**Required/Optional**</span></span>|<span data-ttu-id="93a9d-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="93a9d-110">**Data Type**</span></span>|<span data-ttu-id="93a9d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="93a9d-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="93a9d-112">_code_</span><span class="sxs-lookup"><span data-stu-id="93a9d-112">_code_</span></span> <br/> |<span data-ttu-id="93a9d-113">必需</span><span class="sxs-lookup"><span data-stu-id="93a9d-113">Required</span></span>  <br/> |<span data-ttu-id="93a9d-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="93a9d-114">**Number**</span></span> <br/> | <span data-ttu-id="93a9d-115">文本域格式代码。</span><span class="sxs-lookup"><span data-stu-id="93a9d-115">A text field format code.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="93a9d-116">返回值</span><span class="sxs-lookup"><span data-stu-id="93a9d-116">Return value</span></span>

<span data-ttu-id="93a9d-117">字符串</span><span class="sxs-lookup"><span data-stu-id="93a9d-117">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="93a9d-118">注解</span><span class="sxs-lookup"><span data-stu-id="93a9d-118">Remarks</span></span>

<span data-ttu-id="93a9d-119">格式图片字符串用于 FORMAT 函数中，可以定义日期、时间、数字和单位标签的扩展值。</span><span class="sxs-lookup"><span data-stu-id="93a9d-119">Format picture strings are used in the FORMAT function to define the expansion of values to dates, times, numbers, and unit labels.</span></span>
  
## <a name="example"></a><span data-ttu-id="93a9d-120">示例</span><span class="sxs-lookup"><span data-stu-id="93a9d-120">Example</span></span>

<span data-ttu-id="93a9d-121">FIELDPICTURE (0)</span><span class="sxs-lookup"><span data-stu-id="93a9d-121">FIELDPICTURE(0)</span></span> 
  
<span data-ttu-id="93a9d-122">返回格式图片字符串“esc(0)”，当在 FORMAT 函数中使用时，指定了带有一个小数位和小写字母单位说明的数字。</span><span class="sxs-lookup"><span data-stu-id="93a9d-122">Returns the format picture string "esc(0)", which specifies a number that has one decimal place and a lowercase unit description when used in the FORMAT function.</span></span> 
  

