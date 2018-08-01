---
title: 使用宏进行错误处理
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 351405ca-b72b-4e9e-bc8e-947344588970
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c4e216f2204f4ee97d9eeac81f77ce6a82fff3f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779068"
---
# <a name="using-macros-for-error-handling"></a><span data-ttu-id="3f42d-103">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="3f42d-103">Using Macros for Error Handling</span></span>

  
  
<span data-ttu-id="3f42d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3f42d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3f42d-105">有几个宏的更方便地处理的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="3f42d-105">There are several macros for making it easier to work with HRESULT values.</span></span>
  
<span data-ttu-id="3f42d-106">有两组测试故障或成功的宏： HR_SUCCEEDED 和 HR_FAILED 和成功和失败。</span><span class="sxs-lookup"><span data-stu-id="3f42d-106">There are two sets of macros that test for failure or success: HR_SUCCEEDED and HR_FAILED and SUCCEEDED and FAILED.</span></span> <span data-ttu-id="3f42d-107">成功是 HR_SUCCEEDED 和失败相同 HR_FAILED 相同。</span><span class="sxs-lookup"><span data-stu-id="3f42d-107">SUCCEEDED is the same as HR_SUCCEEDED and FAILED is the same as HR_FAILED.</span></span>
  
<span data-ttu-id="3f42d-108">在这种情况下，使用**ResultFromScode**宏 S_OK HRESULT 变量设置为相应的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="3f42d-108">In this case, use the **ResultFromScode** macro to set the HRESULT variable to the corresponding HRESULT value for S_OK.</span></span> 
  
<span data-ttu-id="3f42d-109">下表简要介绍常用的宏。</span><span class="sxs-lookup"><span data-stu-id="3f42d-109">Commonly used macros are briefly described in the following table.</span></span>
  
|<span data-ttu-id="3f42d-110">**宏**</span><span class="sxs-lookup"><span data-stu-id="3f42d-110">**Macro**</span></span>|<span data-ttu-id="3f42d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="3f42d-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f42d-112">**MAKE_HRESULT**</span><span class="sxs-lookup"><span data-stu-id="3f42d-112">**MAKE_HRESULT**</span></span> <br/> |<span data-ttu-id="3f42d-113">构造 HRESULT 从及其组件。</span><span class="sxs-lookup"><span data-stu-id="3f42d-113">Constructs an HRESULT from its components.</span></span>  <br/> |
|<span data-ttu-id="3f42d-114">**HR_SUCCEEDED**</span><span class="sxs-lookup"><span data-stu-id="3f42d-114">**HR_SUCCEEDED**</span></span> <br/> |<span data-ttu-id="3f42d-115">测试 HRESULT 成功或警告条件。</span><span class="sxs-lookup"><span data-stu-id="3f42d-115">Tests an HRESULT for a success or warning condition.</span></span>  <br/> |
|<span data-ttu-id="3f42d-116">**HR_FAILED**</span><span class="sxs-lookup"><span data-stu-id="3f42d-116">**HR_FAILED**</span></span> <br/> |<span data-ttu-id="3f42d-117">测试 HRESULT 错误条件。</span><span class="sxs-lookup"><span data-stu-id="3f42d-117">Tests an HRESULT for an error condition.</span></span>  <br/> |
|<span data-ttu-id="3f42d-118">**HRESULT_CODE**</span><span class="sxs-lookup"><span data-stu-id="3f42d-118">**HRESULT_CODE**</span></span> <br/> |<span data-ttu-id="3f42d-119">提取 HRESULT 的错误代码部分。</span><span class="sxs-lookup"><span data-stu-id="3f42d-119">Extracts the error code part of the HRESULT.</span></span>  <br/> |
|<span data-ttu-id="3f42d-120">**HRESULT_FACILITY**</span><span class="sxs-lookup"><span data-stu-id="3f42d-120">**HRESULT_FACILITY**</span></span> <br/> |<span data-ttu-id="3f42d-121">从 HRESULT 提取实用工具。</span><span class="sxs-lookup"><span data-stu-id="3f42d-121">Extracts the facility from the HRESULT.</span></span>  <br/> |
|<span data-ttu-id="3f42d-122">**HRESULT_SEVERITY**</span><span class="sxs-lookup"><span data-stu-id="3f42d-122">**HRESULT_SEVERITY**</span></span> <br/> |<span data-ttu-id="3f42d-123">从严重提取严重性位。</span><span class="sxs-lookup"><span data-stu-id="3f42d-123">Extracts the severity bit from the SEVERITY.</span></span>  <br/> |
|<span data-ttu-id="3f42d-124">**成功**</span><span class="sxs-lookup"><span data-stu-id="3f42d-124">**SUCCEEDED**</span></span> <br/> |<span data-ttu-id="3f42d-125">测试 HRESULT 成功或警告条件。</span><span class="sxs-lookup"><span data-stu-id="3f42d-125">Tests an HRESULT for a success or warning condition.</span></span>  <br/> |
|<span data-ttu-id="3f42d-126">**失败**</span><span class="sxs-lookup"><span data-stu-id="3f42d-126">**FAILED**</span></span> <br/> |<span data-ttu-id="3f42d-127">测试 HRESULT 错误条件。</span><span class="sxs-lookup"><span data-stu-id="3f42d-127">Tests an HRESULT for an error condition.</span></span>  <br/> |
   

