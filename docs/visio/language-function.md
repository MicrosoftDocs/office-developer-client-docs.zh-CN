---
title: LANGUAGE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e372c670-e9a0-4352-b70a-3a054b036124
description: 允许在不同语言表示形式之间进行比较操作。 它最适用于将 Internet 工程任务组的语言标记 (BCP 47) 值转换为区域设置 id (LCID) 值。
ms.openlocfilehash: 9c2dc96cefe7a1cfcd06947dcc54453dcef276fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424748"
---
# <a name="language-function"></a><span data-ttu-id="4798b-104">LANGUAGE 函数</span><span class="sxs-lookup"><span data-stu-id="4798b-104">LANGUAGE Function</span></span>

<span data-ttu-id="4798b-105">允许在不同语言表示形式之间进行比较操作。</span><span class="sxs-lookup"><span data-stu-id="4798b-105">Allows comparison operations between different language representations.</span></span> <span data-ttu-id="4798b-106">它最适用于将 Internet 工程任务组的语言标记 (BCP 47) 值转换为区域设置 id (LCID) 值。</span><span class="sxs-lookup"><span data-stu-id="4798b-106">It is best used for converting Internet Engineering Task Force language tags (BCP 47) values to locale id (LCID) values.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="4798b-107">版本信息</span><span class="sxs-lookup"><span data-stu-id="4798b-107">Version Information</span></span>

<span data-ttu-id="4798b-108">添加的版本： Visio 2013
</span><span class="sxs-lookup"><span data-stu-id="4798b-108">Version Added: Visio 2013</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="4798b-109">语法</span><span class="sxs-lookup"><span data-stu-id="4798b-109">Syntax</span></span>

 <span data-ttu-id="4798b-110">**语言**( _lcid_or_bcp47_)</span><span class="sxs-lookup"><span data-stu-id="4798b-110">**LANGUAGE**( _lcid_or_bcp47_)</span></span>
  
### <a name="parameters"></a><span data-ttu-id="4798b-111">参数</span><span class="sxs-lookup"><span data-stu-id="4798b-111">Parameters</span></span>

|<span data-ttu-id="4798b-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="4798b-112">**Name**</span></span>|<span data-ttu-id="4798b-113">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="4798b-113">**Required/Optional**</span></span>|<span data-ttu-id="4798b-114">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4798b-114">**Data Type**</span></span>|<span data-ttu-id="4798b-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="4798b-115">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4798b-116">_lcid_or_bcp47_</span><span class="sxs-lookup"><span data-stu-id="4798b-116">_lcid_or_bcp47_</span></span> <br/> |<span data-ttu-id="4798b-117">必需</span><span class="sxs-lookup"><span data-stu-id="4798b-117">Required</span></span>  <br/> |<span data-ttu-id="4798b-118">**String**</span><span class="sxs-lookup"><span data-stu-id="4798b-118">**String**</span></span> <br/> |<span data-ttu-id="4798b-119">语言的 LCID 或 BCP 47 值。</span><span class="sxs-lookup"><span data-stu-id="4798b-119">The LCID or BCP 47 value for the language.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="4798b-120">返回值</span><span class="sxs-lookup"><span data-stu-id="4798b-120">Return value</span></span>

<span data-ttu-id="4798b-121">整数</span><span class="sxs-lookup"><span data-stu-id="4798b-121">Integer</span></span>
  
## <a name="example"></a><span data-ttu-id="4798b-122">示例</span><span class="sxs-lookup"><span data-stu-id="4798b-122">Example</span></span>

 `LANGUAGE("en-us")`
  
<span data-ttu-id="4798b-123">返回值为 "1033"。</span><span class="sxs-lookup"><span data-stu-id="4798b-123">Returns a value of '1033'.</span></span>
  
 `LANGUAGE("es-es")`
  
<span data-ttu-id="4798b-124">返回值为 "3082"。</span><span class="sxs-lookup"><span data-stu-id="4798b-124">Returns a value of '3082'.</span></span>
  

