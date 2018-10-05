---
title: MAPI 中的错误处理
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 99e2c485-af84-46f4-84b4-fca2117b5a21
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 98ee0856411cce3a3e9012185be6c30503de7779
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401690"
---
# <a name="error-handling-in-mapi"></a><span data-ttu-id="16abf-103">MAPI 中的错误处理</span><span class="sxs-lookup"><span data-stu-id="16abf-103">Error handling in MAPI</span></span>

<span data-ttu-id="16abf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="16abf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="16abf-105">使用 32 位数字，因此已知句柄或 HRESULT 返回成功、 警告和错误值。</span><span class="sxs-lookup"><span data-stu-id="16abf-105">Success, warning, and error values are returned using a 32-bit number known as a result handle, or HRESULT.</span></span> <span data-ttu-id="16abf-106">HRESULT 不真正是任何; 句柄它是只具有编码值中的多个字段的 32 位值。</span><span class="sxs-lookup"><span data-stu-id="16abf-106">An HRESULT is really not a handle to anything; it is merely a 32-bit value with several fields encoded in the value.</span></span> <span data-ttu-id="16abf-107">零结果指示成功和非零结果指示故障。</span><span class="sxs-lookup"><span data-stu-id="16abf-107">A zero result indicates success and a nonzero result indicates failure.</span></span>
  
<span data-ttu-id="16abf-108">在 32 位平台上的 MAPI 仅适用于 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="16abf-108">MAPI on 32-bit platforms works solely with HRESULT values.</span></span>
  
<span data-ttu-id="16abf-109">下图显示了 32 位平台的 HRESULT 格式。</span><span class="sxs-lookup"><span data-stu-id="16abf-109">The following illustration shows the HRESULT format for 32-bit platforms.</span></span>
  
<span data-ttu-id="16abf-110">**HRESULT 格式**</span><span class="sxs-lookup"><span data-stu-id="16abf-110">**HRESULT format**</span></span>
  
<span data-ttu-id="16abf-111">![HRESULT 格式](media/amapi_49.gif "HRESULT 格式")</span><span class="sxs-lookup"><span data-stu-id="16abf-111">![HRESULT format](media/amapi_49.gif "HRESULT format")</span></span>
  
<span data-ttu-id="16abf-112">在 HRESULT 高位指示返回的值是否表示成功或失败。</span><span class="sxs-lookup"><span data-stu-id="16abf-112">The high order bit in the HRESULT indicates whether the return value represents success or failure.</span></span> <span data-ttu-id="16abf-113">如果设置为零，则值指示成功。</span><span class="sxs-lookup"><span data-stu-id="16abf-113">If set to zero, the value indicates success.</span></span> <span data-ttu-id="16abf-114">如果设置为 1，则表明失败。</span><span class="sxs-lookup"><span data-stu-id="16abf-114">If set to 1, it indicates failure.</span></span>
  
<span data-ttu-id="16abf-115">R、 C、 N 和 r 位 HRESULT 中保留。</span><span class="sxs-lookup"><span data-stu-id="16abf-115">The R, C, N, and r bits are reserved in the HRESULT.</span></span>
  
<span data-ttu-id="16abf-116">两个版本中的设施字段指示错误的责任的区域。</span><span class="sxs-lookup"><span data-stu-id="16abf-116">The facility field in both versions indicates the area of responsibility for the error.</span></span> <span data-ttu-id="16abf-117">有几个设施，但绝大多数 MAPI 错误使用 FACILITY_ITF 表示界面错误。</span><span class="sxs-lookup"><span data-stu-id="16abf-117">There are several facilities, but the vast majority of MAPI errors use FACILITY_ITF to represent interface errors.</span></span> <span data-ttu-id="16abf-118">当前使用的最常见功能是： FACILITY_NULL、 FACILITY_ITF、 FACILITY_DISPATCH、 FACILITY_RPC 和 FACILITY_STORAGE。</span><span class="sxs-lookup"><span data-stu-id="16abf-118">The most common facilities that are currently used are: FACILITY_NULL, FACILITY_ITF, FACILITY_DISPATCH, FACILITY_RPC, and FACILITY_STORAGE.</span></span> <span data-ttu-id="16abf-119">如果新设施是必需的 Microsoft 分配因为他们需要是唯一的。</span><span class="sxs-lookup"><span data-stu-id="16abf-119">If new facilities are necessary, Microsoft allocates them because they need to be unique.</span></span> <span data-ttu-id="16abf-120">下表介绍了各种的设施字段。</span><span class="sxs-lookup"><span data-stu-id="16abf-120">The following table describes the various facility fields.</span></span>
  
|<span data-ttu-id="16abf-121">设施</span><span class="sxs-lookup"><span data-stu-id="16abf-121">Facility</span></span>|<span data-ttu-id="16abf-122">说明</span><span class="sxs-lookup"><span data-stu-id="16abf-122">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="16abf-123">FACILITY_NULL</span><span class="sxs-lookup"><span data-stu-id="16abf-123">FACILITY_NULL</span></span>  <br/> |<span data-ttu-id="16abf-124">广泛适用常见的状态代码，如 S_OK 或 E_OUTOF_MEMORY;值为零。</span><span class="sxs-lookup"><span data-stu-id="16abf-124">For broadly applicable common status codes such as S_OK or E_OUTOF_MEMORY; the value is zero.</span></span>  <br/> |
|<span data-ttu-id="16abf-125">FACILITY_ITF</span><span class="sxs-lookup"><span data-stu-id="16abf-125">FACILITY_ITF</span></span>  <br/> |<span data-ttu-id="16abf-126">大多数接口方法; 从返回的状态代码由接口定义值。</span><span class="sxs-lookup"><span data-stu-id="16abf-126">For most status codes returned from interface methods; the value is defined by the interface.</span></span> <span data-ttu-id="16abf-127">即两个的 HRESULT 值完全相同 32 位的值从两个不同接口返回的可能有不同的含义。</span><span class="sxs-lookup"><span data-stu-id="16abf-127">That is, two HRESULT values with exactly the same 32-bit value returned from two different interfaces might have different meanings.</span></span>  <br/> |
|<span data-ttu-id="16abf-128">FACILITY_DISPATCH</span><span class="sxs-lookup"><span data-stu-id="16abf-128">FACILITY_DISPATCH</span></span>  <br/> |<span data-ttu-id="16abf-129">为后期绑定[IDispatch](https://msdn.microsoft.com/library/ms221608.aspx)接口错误。</span><span class="sxs-lookup"><span data-stu-id="16abf-129">For late binding [IDispatch](https://msdn.microsoft.com/library/ms221608.aspx) interface errors.</span></span>  <br/> |
|<span data-ttu-id="16abf-130">FACILITY_RPC</span><span class="sxs-lookup"><span data-stu-id="16abf-130">FACILITY_RPC</span></span>  <br/> |<span data-ttu-id="16abf-131">有关从远程过程调用的返回状态代码。</span><span class="sxs-lookup"><span data-stu-id="16abf-131">For status codes returned from remote procedure calls.</span></span>  <br/> |
|<span data-ttu-id="16abf-132">FACILITY_STORAGE</span><span class="sxs-lookup"><span data-stu-id="16abf-132">FACILITY_STORAGE</span></span>  <br/> |<span data-ttu-id="16abf-133">从与结构化存储有关[IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx)或[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)方法调用返回的状态代码。</span><span class="sxs-lookup"><span data-stu-id="16abf-133">For status codes returned from [IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx) or [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) method calls relating to structured storage.</span></span> <span data-ttu-id="16abf-134">状态代码中的范围的 Windows 错误代码的代码 （低 16 位） 值 (即，少于 256 个) 为相应的 Windows 错误意义相同。</span><span class="sxs-lookup"><span data-stu-id="16abf-134">Status codes with code (lower 16 bits) values in the range of Windows error codes (that is, less than 256) have the same meaning as the corresponding Windows errors.</span></span>  <br/> |
   
<span data-ttu-id="16abf-135">代码字段是分配表示错误或警告的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="16abf-135">The code field is a unique number that is assigned to represent the error or warning.</span></span>
  

