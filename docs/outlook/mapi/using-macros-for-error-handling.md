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
ms.openlocfilehash: 9e6901d6583e7a7924a4a7c19c0a262bcef74bd3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329656"
---
# <a name="using-macros-for-error-handling"></a><span data-ttu-id="6b4f4-103">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="6b4f4-103">Using Macros for Error Handling</span></span>

  
  
<span data-ttu-id="6b4f4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6b4f4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6b4f4-105">有几个宏可让您更轻松地使用 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-105">There are several macros for making it easier to work with HRESULT values.</span></span>
  
<span data-ttu-id="6b4f4-106">有两组宏可测试是否出现故障或成功: HR_SUCCEEDED 和 HR_FAILED, 并且已成功和失败。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-106">There are two sets of macros that test for failure or success: HR_SUCCEEDED and HR_FAILED and SUCCEEDED and FAILED.</span></span> <span data-ttu-id="6b4f4-107">SUCCEEDED 与 HR_SUCCEEDED 相同, 失败与 HR_FAILED 相同。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-107">SUCCEEDED is the same as HR_SUCCEEDED and FAILED is the same as HR_FAILED.</span></span>
  
<span data-ttu-id="6b4f4-108">在这种情况下, 使用**ResultFromScode**宏将 hresult 变量设置为 S_OK 的相应 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-108">In this case, use the **ResultFromScode** macro to set the HRESULT variable to the corresponding HRESULT value for S_OK.</span></span> 
  
<span data-ttu-id="6b4f4-109">常用的宏将在下表中简要说明。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-109">Commonly used macros are briefly described in the following table.</span></span>
  
|<span data-ttu-id="6b4f4-110">**宏**</span><span class="sxs-lookup"><span data-stu-id="6b4f4-110">**Macro**</span></span>|<span data-ttu-id="6b4f4-111">**Description**</span><span class="sxs-lookup"><span data-stu-id="6b4f4-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6b4f4-112">**MAKE_HRESULT**</span><span class="sxs-lookup"><span data-stu-id="6b4f4-112">**MAKE_HRESULT**</span></span> <br/> |<span data-ttu-id="6b4f4-113">从其组件构造 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-113">Constructs an HRESULT from its components.</span></span>  <br/> |
|<span data-ttu-id="6b4f4-114">**HR_SUCCEEDED**</span><span class="sxs-lookup"><span data-stu-id="6b4f4-114">**HR_SUCCEEDED**</span></span> <br/> |<span data-ttu-id="6b4f4-115">测试 HRESULT 的成功或警告条件。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-115">Tests an HRESULT for a success or warning condition.</span></span>  <br/> |
|<span data-ttu-id="6b4f4-116">**HR_FAILED**</span><span class="sxs-lookup"><span data-stu-id="6b4f4-116">**HR_FAILED**</span></span> <br/> |<span data-ttu-id="6b4f4-117">测试错误条件的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-117">Tests an HRESULT for an error condition.</span></span>  <br/> |
|<span data-ttu-id="6b4f4-118">**HRESULT_CODE**</span><span class="sxs-lookup"><span data-stu-id="6b4f4-118">**HRESULT_CODE**</span></span> <br/> |<span data-ttu-id="6b4f4-119">提取 HRESULT 的错误代码部分。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-119">Extracts the error code part of the HRESULT.</span></span>  <br/> |
|<span data-ttu-id="6b4f4-120">**HRESULT_FACILITY**</span><span class="sxs-lookup"><span data-stu-id="6b4f4-120">**HRESULT_FACILITY**</span></span> <br/> |<span data-ttu-id="6b4f4-121">从 HRESULT 中提取功能。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-121">Extracts the facility from the HRESULT.</span></span>  <br/> |
|<span data-ttu-id="6b4f4-122">**HRESULT_SEVERITY**</span><span class="sxs-lookup"><span data-stu-id="6b4f4-122">**HRESULT_SEVERITY**</span></span> <br/> |<span data-ttu-id="6b4f4-123">从严重性中提取严重度位。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-123">Extracts the severity bit from the SEVERITY.</span></span>  <br/> |
|<span data-ttu-id="6b4f4-124">**完成**</span><span class="sxs-lookup"><span data-stu-id="6b4f4-124">**SUCCEEDED**</span></span> <br/> |<span data-ttu-id="6b4f4-125">测试 HRESULT 的成功或警告条件。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-125">Tests an HRESULT for a success or warning condition.</span></span>  <br/> |
|<span data-ttu-id="6b4f4-126">**未能**</span><span class="sxs-lookup"><span data-stu-id="6b4f4-126">**FAILED**</span></span> <br/> |<span data-ttu-id="6b4f4-127">测试错误条件的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-127">Tests an HRESULT for an error condition.</span></span>  <br/> |
   

