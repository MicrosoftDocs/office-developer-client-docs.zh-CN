---
title: FONT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 20b587ee-87bf-4648-99ec-ddedd703d9fd
description: 返回由名称指定的字体的唯一标识符的整数值。
ms.openlocfilehash: 7ae6fe6dc8bb9c718a358d11d4a6a0227eaf18df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422171"
---
# <a name="font-function"></a><span data-ttu-id="e2780-103">FONT 函数</span><span class="sxs-lookup"><span data-stu-id="e2780-103">FONT Function</span></span>

<span data-ttu-id="e2780-104">返回由名称指定的字体的唯一标识符的整数值。</span><span class="sxs-lookup"><span data-stu-id="e2780-104">Returns the integer value of the unique identifier for a font, specified by name.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2780-105">在大多数情况下，字体标识符是特定于系统的。</span><span class="sxs-lookup"><span data-stu-id="e2780-105">In most cases, the font identifier is system-specific.</span></span> <span data-ttu-id="e2780-106">尽管字体在文件中一旦使用就仍然保持建立，**但 FONT** 函数提供了跨系统和版本对特定字体的一致Visio。</span><span class="sxs-lookup"><span data-stu-id="e2780-106">Although the font remains established once used in a file, the **FONT** function provides consistent access to a particular font across systems and versions of Visio.</span></span> <span data-ttu-id="e2780-107">建议使用 **FONT** 函数分配字体，而不是直接引用字体标识符。</span><span class="sxs-lookup"><span data-stu-id="e2780-107">It is recommended that you use the **FONT** function to assign fonts instead of referring to font identifiers directly.</span></span> 
  
## <a name="version-information"></a><span data-ttu-id="e2780-108">版本信息</span><span class="sxs-lookup"><span data-stu-id="e2780-108">Version Information</span></span>

<span data-ttu-id="e2780-109">添加的版本： Visio 2013
</span><span class="sxs-lookup"><span data-stu-id="e2780-109">Version Added: Visio 2013</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e2780-110">语法</span><span class="sxs-lookup"><span data-stu-id="e2780-110">Syntax</span></span>

 <span data-ttu-id="e2780-111">**FONT** ( _"font_name_string"_) </span><span class="sxs-lookup"><span data-stu-id="e2780-111">**FONT**( _"font_name_string"_)</span></span>
  
### <a name="parameters"></a><span data-ttu-id="e2780-112">参数</span><span class="sxs-lookup"><span data-stu-id="e2780-112">Parameters</span></span>

|<span data-ttu-id="e2780-113">**名称**</span><span class="sxs-lookup"><span data-stu-id="e2780-113">**Name**</span></span>|<span data-ttu-id="e2780-114">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="e2780-114">**Required/Optional**</span></span>|<span data-ttu-id="e2780-115">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e2780-115">**Data Type**</span></span>|<span data-ttu-id="e2780-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="e2780-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e2780-117">_font_name_string_</span><span class="sxs-lookup"><span data-stu-id="e2780-117">_font_name_string_</span></span> <br/> |<span data-ttu-id="e2780-118">必需</span><span class="sxs-lookup"><span data-stu-id="e2780-118">Required</span></span>  <br/> |<span data-ttu-id="e2780-119">**string**</span><span class="sxs-lookup"><span data-stu-id="e2780-119">**string**</span></span> <br/> |<span data-ttu-id="e2780-120">字体的名称。</span><span class="sxs-lookup"><span data-stu-id="e2780-120">The name of the font.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="e2780-121">返回值</span><span class="sxs-lookup"><span data-stu-id="e2780-121">Return value</span></span>

<span data-ttu-id="e2780-122">整数</span><span class="sxs-lookup"><span data-stu-id="e2780-122">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e2780-123">备注</span><span class="sxs-lookup"><span data-stu-id="e2780-123">Remarks</span></span>

<span data-ttu-id="e2780-124">如果为  *指定字体font_name_string*  字符串与已知字体不匹配，则此函数将返回#VALUE！</span><span class="sxs-lookup"><span data-stu-id="e2780-124">If the string provided for  *font_name_string*  does not match a known font, this function returns a #VALUE!</span></span> <span data-ttu-id="e2780-125">error。</span><span class="sxs-lookup"><span data-stu-id="e2780-125">error.</span></span> 
  
## <a name="example"></a><span data-ttu-id="e2780-126">示例</span><span class="sxs-lookup"><span data-stu-id="e2780-126">Example</span></span>

 `FONT("Calibri")`
  
<span data-ttu-id="e2780-127">返回整数值 (4) 表示"Calibri"字体的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="e2780-127">Returns the integer value (4) representing the unique ID for the "Calibri" font.</span></span>
  

