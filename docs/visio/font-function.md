---
title: FONT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 20b587ee-87bf-4648-99ec-ddedd703d9fd
description: 返回由 name 指定字体的唯一标识符的整数值。
ms.openlocfilehash: 4afd2aa05f2103675bf0df8db5cc7ea21f45fe71
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780296"
---
# <a name="font-function"></a><span data-ttu-id="f64c6-103">FONT 函数</span><span class="sxs-lookup"><span data-stu-id="f64c6-103">FONT Function</span></span>

<span data-ttu-id="f64c6-104">返回由 name 指定字体的唯一标识符的整数值。</span><span class="sxs-lookup"><span data-stu-id="f64c6-104">Returns the integer value of the unique identifier for a font, specified by name.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f64c6-105">在大多数情况下，字体标识符是特定于系统的。</span><span class="sxs-lookup"><span data-stu-id="f64c6-105">In most cases, the font identifier is system-specific.</span></span> <span data-ttu-id="f64c6-106">尽管字体保持已一次文件中使用，**字体**函数提供对特定字体具有跨系统和版本的 Visio 一致的访问。</span><span class="sxs-lookup"><span data-stu-id="f64c6-106">Although the font remains established once used in a file, the **FONT** function provides consistent access to a particular font across systems and versions of Visio.</span></span> <span data-ttu-id="f64c6-107">建议使用的**字体**函数分配而不是直接引用字体标识符的字体。</span><span class="sxs-lookup"><span data-stu-id="f64c6-107">It is recommended that you use the **FONT** function to assign fonts instead of referring to font identifiers directly.</span></span> 
  
## <a name="version-information"></a><span data-ttu-id="f64c6-108">版本信息</span><span class="sxs-lookup"><span data-stu-id="f64c6-108">Version Information</span></span>

<span data-ttu-id="f64c6-109">添加的版本： Visio 2013
</span><span class="sxs-lookup"><span data-stu-id="f64c6-109">Version Added: Visio 2013</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="f64c6-110">语法</span><span class="sxs-lookup"><span data-stu-id="f64c6-110">Syntax</span></span>

 <span data-ttu-id="f64c6-111">**字体**( _"font_name_string"_)</span><span class="sxs-lookup"><span data-stu-id="f64c6-111">**FONT**( _"font_name_string"_)</span></span>
  
### <a name="parameters"></a><span data-ttu-id="f64c6-112">参数</span><span class="sxs-lookup"><span data-stu-id="f64c6-112">Parameters</span></span>

|<span data-ttu-id="f64c6-113">**名称**</span><span class="sxs-lookup"><span data-stu-id="f64c6-113">**Name**</span></span>|<span data-ttu-id="f64c6-114">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f64c6-114">**Required/Optional**</span></span>|<span data-ttu-id="f64c6-115">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f64c6-115">**Data Type**</span></span>|<span data-ttu-id="f64c6-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="f64c6-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f64c6-117">_font_name_string_</span><span class="sxs-lookup"><span data-stu-id="f64c6-117">_font_name_string_</span></span> <br/> |<span data-ttu-id="f64c6-118">必需</span><span class="sxs-lookup"><span data-stu-id="f64c6-118">Required</span></span>  <br/> |<span data-ttu-id="f64c6-119">**string**</span><span class="sxs-lookup"><span data-stu-id="f64c6-119">**string**</span></span> <br/> |<span data-ttu-id="f64c6-120">字体的名称。</span><span class="sxs-lookup"><span data-stu-id="f64c6-120">The name of the font.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="f64c6-121">返回值</span><span class="sxs-lookup"><span data-stu-id="f64c6-121">Return value</span></span>

<span data-ttu-id="f64c6-122">Integer</span><span class="sxs-lookup"><span data-stu-id="f64c6-122">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f64c6-123">说明</span><span class="sxs-lookup"><span data-stu-id="f64c6-123">Remarks</span></span>

<span data-ttu-id="f64c6-124">如果为*font_name_string*提供的字符串与已知的字体不匹配，则此函数返回 #VALUE ！</span><span class="sxs-lookup"><span data-stu-id="f64c6-124">If the string provided for  *font_name_string*  does not match a known font, this function returns a #VALUE!</span></span> <span data-ttu-id="f64c6-125">错误。</span><span class="sxs-lookup"><span data-stu-id="f64c6-125">error.</span></span> 
  
## <a name="example"></a><span data-ttu-id="f64c6-126">示例</span><span class="sxs-lookup"><span data-stu-id="f64c6-126">Example</span></span>

 `FONT("Calibri")`
  
<span data-ttu-id="f64c6-127">返回表示"宋体"字体的唯一 ID 的整数值 (4)。</span><span class="sxs-lookup"><span data-stu-id="f64c6-127">Returns the integer value (4) representing the unique ID for the "Calibri" font.</span></span>
  

