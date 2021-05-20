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
description: 返回一个格式图片字符串，该字符串与 Microsoft Visio文本字段格式代码匹配。
ms.openlocfilehash: 1ab24c602c7975cf6be22a564a8b9ee9aa0d6f46
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431454"
---
# <a name="fieldpicture-function"></a><span data-ttu-id="7fa88-103">FIELDPICTURE 函数</span><span class="sxs-lookup"><span data-stu-id="7fa88-103">FIELDPICTURE Function</span></span>

<span data-ttu-id="7fa88-104">返回一个格式图片字符串，该字符串与 Microsoft Visio文本字段格式代码匹配。</span><span class="sxs-lookup"><span data-stu-id="7fa88-104">Returns a format-picture string that matches the Microsoft Visio internal text field format code.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="7fa88-105">语法</span><span class="sxs-lookup"><span data-stu-id="7fa88-105">Syntax</span></span>

<span data-ttu-id="7fa88-106">FIELDPICTURE (\*\* *code* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="7fa88-106">FIELDPICTURE(\*\* *code* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="7fa88-107">参数</span><span class="sxs-lookup"><span data-stu-id="7fa88-107">Parameters</span></span>

|<span data-ttu-id="7fa88-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="7fa88-108">**Name**</span></span>|<span data-ttu-id="7fa88-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="7fa88-109">**Required/Optional**</span></span>|<span data-ttu-id="7fa88-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7fa88-110">**Data Type**</span></span>|<span data-ttu-id="7fa88-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="7fa88-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7fa88-112">_code_</span><span class="sxs-lookup"><span data-stu-id="7fa88-112">_code_</span></span> <br/> |<span data-ttu-id="7fa88-113">必需</span><span class="sxs-lookup"><span data-stu-id="7fa88-113">Required</span></span>  <br/> |<span data-ttu-id="7fa88-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="7fa88-114">**Number**</span></span> <br/> | <span data-ttu-id="7fa88-115">文本域格式代码。</span><span class="sxs-lookup"><span data-stu-id="7fa88-115">A text field format code.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="7fa88-116">返回值</span><span class="sxs-lookup"><span data-stu-id="7fa88-116">Return value</span></span>

<span data-ttu-id="7fa88-117">String</span><span class="sxs-lookup"><span data-stu-id="7fa88-117">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7fa88-118">备注</span><span class="sxs-lookup"><span data-stu-id="7fa88-118">Remarks</span></span>

<span data-ttu-id="7fa88-119">格式图片字符串用于 FORMAT 函数中，可以定义日期、时间、数字和单位标签的扩展值。</span><span class="sxs-lookup"><span data-stu-id="7fa88-119">Format picture strings are used in the FORMAT function to define the expansion of values to dates, times, numbers, and unit labels.</span></span>
  
## <a name="example"></a><span data-ttu-id="7fa88-120">示例</span><span class="sxs-lookup"><span data-stu-id="7fa88-120">Example</span></span>

<span data-ttu-id="7fa88-121">FIELDPICTURE (0) </span><span class="sxs-lookup"><span data-stu-id="7fa88-121">FIELDPICTURE(0)</span></span> 
  
<span data-ttu-id="7fa88-122">返回格式图片字符串“esc(0)”，当在 FORMAT 函数中使用时，指定了带有一个小数位和小写字母单位说明的数字。</span><span class="sxs-lookup"><span data-stu-id="7fa88-122">Returns the format picture string "esc(0)", which specifies a number that has one decimal place and a lowercase unit description when used in the FORMAT function.</span></span> 
  

