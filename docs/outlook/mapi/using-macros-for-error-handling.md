---
title: 使用宏处理错误
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 351405ca-b72b-4e9e-bc8e-947344588970
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9e6901d6583e7a7924a4a7c19c0a262bcef74bd3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435563"
---
# <a name="using-macros-for-error-handling"></a><span data-ttu-id="abf55-103">使用宏处理错误</span><span class="sxs-lookup"><span data-stu-id="abf55-103">Using Macros for Error Handling</span></span>

  
  
<span data-ttu-id="abf55-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="abf55-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="abf55-105">有几个宏可以更轻松地使用 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="abf55-105">There are several macros for making it easier to work with HRESULT values.</span></span>
  
<span data-ttu-id="abf55-106">有两组宏用于测试失败或成功：HR_SUCCEEDED和HR_FAILED SUCCEEDED 和 FAILED。</span><span class="sxs-lookup"><span data-stu-id="abf55-106">There are two sets of macros that test for failure or success: HR_SUCCEEDED and HR_FAILED and SUCCEEDED and FAILED.</span></span> <span data-ttu-id="abf55-107">SUCCEEDED 与 HR_SUCCEEDED 相同，FAILED 与 HR_FAILED。</span><span class="sxs-lookup"><span data-stu-id="abf55-107">SUCCEEDED is the same as HR_SUCCEEDED and FAILED is the same as HR_FAILED.</span></span>
  
<span data-ttu-id="abf55-108">在这种情况下，使用 **ResultFromScode** 宏将 HRESULT 变量设置为相应的 HRESULT S_OK。</span><span class="sxs-lookup"><span data-stu-id="abf55-108">In this case, use the **ResultFromScode** macro to set the HRESULT variable to the corresponding HRESULT value for S_OK.</span></span> 
  
<span data-ttu-id="abf55-109">下表简要介绍了常用的宏。</span><span class="sxs-lookup"><span data-stu-id="abf55-109">Commonly used macros are briefly described in the following table.</span></span>
  
|<span data-ttu-id="abf55-110">**宏**</span><span class="sxs-lookup"><span data-stu-id="abf55-110">**Macro**</span></span>|<span data-ttu-id="abf55-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="abf55-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="abf55-112">**MAKE_HRESULT**</span><span class="sxs-lookup"><span data-stu-id="abf55-112">**MAKE_HRESULT**</span></span> <br/> |<span data-ttu-id="abf55-113">从组件构造 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="abf55-113">Constructs an HRESULT from its components.</span></span>  <br/> |
|<span data-ttu-id="abf55-114">**HR_SUCCEEDED**</span><span class="sxs-lookup"><span data-stu-id="abf55-114">**HR_SUCCEEDED**</span></span> <br/> |<span data-ttu-id="abf55-115">测试 HRESULT 是否成功或警告条件。</span><span class="sxs-lookup"><span data-stu-id="abf55-115">Tests an HRESULT for a success or warning condition.</span></span>  <br/> |
|<span data-ttu-id="abf55-116">**HR_FAILED**</span><span class="sxs-lookup"><span data-stu-id="abf55-116">**HR_FAILED**</span></span> <br/> |<span data-ttu-id="abf55-117">测试错误条件的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="abf55-117">Tests an HRESULT for an error condition.</span></span>  <br/> |
|<span data-ttu-id="abf55-118">**HRESULT_CODE**</span><span class="sxs-lookup"><span data-stu-id="abf55-118">**HRESULT_CODE**</span></span> <br/> |<span data-ttu-id="abf55-119">提取 HRESULT 的错误代码部分。</span><span class="sxs-lookup"><span data-stu-id="abf55-119">Extracts the error code part of the HRESULT.</span></span>  <br/> |
|<span data-ttu-id="abf55-120">**HRESULT_FACILITY**</span><span class="sxs-lookup"><span data-stu-id="abf55-120">**HRESULT_FACILITY**</span></span> <br/> |<span data-ttu-id="abf55-121">从 HRESULT 中提取设施。</span><span class="sxs-lookup"><span data-stu-id="abf55-121">Extracts the facility from the HRESULT.</span></span>  <br/> |
|<span data-ttu-id="abf55-122">**HRESULT_SEVERITY**</span><span class="sxs-lookup"><span data-stu-id="abf55-122">**HRESULT_SEVERITY**</span></span> <br/> |<span data-ttu-id="abf55-123">从 SEVERITY 中提取严重性位。</span><span class="sxs-lookup"><span data-stu-id="abf55-123">Extracts the severity bit from the SEVERITY.</span></span>  <br/> |
|<span data-ttu-id="abf55-124">**SUCCEEDED**</span><span class="sxs-lookup"><span data-stu-id="abf55-124">**SUCCEEDED**</span></span> <br/> |<span data-ttu-id="abf55-125">测试 HRESULT 是否成功或警告条件。</span><span class="sxs-lookup"><span data-stu-id="abf55-125">Tests an HRESULT for a success or warning condition.</span></span>  <br/> |
|<span data-ttu-id="abf55-126">**FAILED**</span><span class="sxs-lookup"><span data-stu-id="abf55-126">**FAILED**</span></span> <br/> |<span data-ttu-id="abf55-127">测试错误条件的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="abf55-127">Tests an HRESULT for an error condition.</span></span>  <br/> |
   

