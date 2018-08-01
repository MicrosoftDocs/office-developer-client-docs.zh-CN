---
title: LANGUAGE Function
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e372c670-e9a0-4352-b70a-3a054b036124
description: 允许不同的语言表示之间的比较操作。 它最适用于将 Internet 工程任务组语言标记 (BCP 47) 值转换为区域设置 id (LCID) 值。
ms.openlocfilehash: 6a05a850f5908ac5a4f6a4a72b2ce56b4c98f137
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780544"
---
# <a name="language-function"></a><span data-ttu-id="90edb-104">LANGUAGE Function</span><span class="sxs-lookup"><span data-stu-id="90edb-104">LANGUAGE Function</span></span>

<span data-ttu-id="90edb-105">允许不同的语言表示之间的比较操作。</span><span class="sxs-lookup"><span data-stu-id="90edb-105">Allows comparison operations between different language representations.</span></span> <span data-ttu-id="90edb-106">它最适用于将 Internet 工程任务组语言标记 (BCP 47) 值转换为区域设置 id (LCID) 值。</span><span class="sxs-lookup"><span data-stu-id="90edb-106">It is best used for converting Internet Engineering Task Force language tags (BCP 47) values to locale id (LCID) values.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="90edb-107">版本信息</span><span class="sxs-lookup"><span data-stu-id="90edb-107">Version Information</span></span>

<span data-ttu-id="90edb-108">添加的版本： Visio 2013
</span><span class="sxs-lookup"><span data-stu-id="90edb-108">Version Added: Visio 2013</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="90edb-109">语法</span><span class="sxs-lookup"><span data-stu-id="90edb-109">Syntax</span></span>

 <span data-ttu-id="90edb-110">**语言**( _lcid_or_bcp47_)</span><span class="sxs-lookup"><span data-stu-id="90edb-110">**LANGUAGE**( _lcid_or_bcp47_)</span></span>
  
### <a name="parameters"></a><span data-ttu-id="90edb-111">参数</span><span class="sxs-lookup"><span data-stu-id="90edb-111">Parameters</span></span>

|<span data-ttu-id="90edb-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="90edb-112">**Name**</span></span>|<span data-ttu-id="90edb-113">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="90edb-113">**Required/Optional**</span></span>|<span data-ttu-id="90edb-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="90edb-114">**Data Type**</span></span>|<span data-ttu-id="90edb-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="90edb-115">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="90edb-116">_lcid_or_bcp47_</span><span class="sxs-lookup"><span data-stu-id="90edb-116">_lcid_or_bcp47_</span></span> <br/> |<span data-ttu-id="90edb-117">必需</span><span class="sxs-lookup"><span data-stu-id="90edb-117">Required</span></span>  <br/> |<span data-ttu-id="90edb-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="90edb-118">**String**</span></span> <br/> |<span data-ttu-id="90edb-119">语言的 LCID 或 BCP 47 值。</span><span class="sxs-lookup"><span data-stu-id="90edb-119">The LCID or BCP 47 value for the language.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="90edb-120">返回值</span><span class="sxs-lookup"><span data-stu-id="90edb-120">Return value</span></span>

<span data-ttu-id="90edb-121">Integer</span><span class="sxs-lookup"><span data-stu-id="90edb-121">Integer</span></span>
  
## <a name="example"></a><span data-ttu-id="90edb-122">示例</span><span class="sxs-lookup"><span data-stu-id="90edb-122">Example</span></span>

 `LANGUAGE("en-us")`
  
<span data-ttu-id="90edb-123">返回的值为"1033"。</span><span class="sxs-lookup"><span data-stu-id="90edb-123">Returns a value of '1033'.</span></span>
  
 `LANGUAGE("es-es")`
  
<span data-ttu-id="90edb-124">返回的值为"3082"。</span><span class="sxs-lookup"><span data-stu-id="90edb-124">Returns a value of '3082'.</span></span>
  

