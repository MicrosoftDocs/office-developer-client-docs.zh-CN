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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287276"
---
# <a name="error-handling-in-mapi"></a><span data-ttu-id="28251-103">MAPI 中的错误处理</span><span class="sxs-lookup"><span data-stu-id="28251-103">Error handling in MAPI</span></span>

<span data-ttu-id="28251-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="28251-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="28251-105">使用称为结果句柄或 HRESULT 的 32 位数字返回成功、警告和错误值。</span><span class="sxs-lookup"><span data-stu-id="28251-105">Success, warning, and error values are returned using a 32-bit number known as a result handle, or HRESULT.</span></span> <span data-ttu-id="28251-106">HRESULT 实际上不是任何句柄;它只是一个 32 位值，值中编码了多个字段。</span><span class="sxs-lookup"><span data-stu-id="28251-106">An HRESULT is really not a handle to anything; it is merely a 32-bit value with several fields encoded in the value.</span></span> <span data-ttu-id="28251-107">零结果表示成功，非零结果表示失败。</span><span class="sxs-lookup"><span data-stu-id="28251-107">A zero result indicates success and a nonzero result indicates failure.</span></span>
  
<span data-ttu-id="28251-108">32 位平台上的 MAPI 仅适用于 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="28251-108">MAPI on 32-bit platforms works solely with HRESULT values.</span></span>
  
<span data-ttu-id="28251-109">下图显示了 32 位平台的 HRESULT 格式。</span><span class="sxs-lookup"><span data-stu-id="28251-109">The following illustration shows the HRESULT format for 32-bit platforms.</span></span>
  
<span data-ttu-id="28251-110">**HRESULT 格式**</span><span class="sxs-lookup"><span data-stu-id="28251-110">**HRESULT format**</span></span>
  
<span data-ttu-id="28251-111">![HRESULT 格式](media/amapi_49.gif "HRESULT 格式")</span><span class="sxs-lookup"><span data-stu-id="28251-111">![HRESULT format](media/amapi_49.gif "HRESULT format")</span></span>
  
<span data-ttu-id="28251-112">HRESULT 中的高顺序位指示返回值是表示成功还是失败。</span><span class="sxs-lookup"><span data-stu-id="28251-112">The high order bit in the HRESULT indicates whether the return value represents success or failure.</span></span> <span data-ttu-id="28251-113">如果设置为零，则值表示成功。</span><span class="sxs-lookup"><span data-stu-id="28251-113">If set to zero, the value indicates success.</span></span> <span data-ttu-id="28251-114">如果设置为 1，则指示失败。</span><span class="sxs-lookup"><span data-stu-id="28251-114">If set to 1, it indicates failure.</span></span>
  
<span data-ttu-id="28251-115">R、C、N 和 r 位保留在 HRESULT 中。</span><span class="sxs-lookup"><span data-stu-id="28251-115">The R, C, N, and r bits are reserved in the HRESULT.</span></span>
  
<span data-ttu-id="28251-116">两个版本中的设备字段都指示错误的责任范围。</span><span class="sxs-lookup"><span data-stu-id="28251-116">The facility field in both versions indicates the area of responsibility for the error.</span></span> <span data-ttu-id="28251-117">有许多设施，但绝大多数 MAPI 错误都FACILITY_ITF接口错误。</span><span class="sxs-lookup"><span data-stu-id="28251-117">There are several facilities, but the vast majority of MAPI errors use FACILITY_ITF to represent interface errors.</span></span> <span data-ttu-id="28251-118">目前最常用的设施包括：FACILITY_NULL、FACILITY_ITF、FACILITY_DISPATCH、FACILITY_RPC 和 FACILITY_STORAGE。</span><span class="sxs-lookup"><span data-stu-id="28251-118">The most common facilities that are currently used are: FACILITY_NULL, FACILITY_ITF, FACILITY_DISPATCH, FACILITY_RPC, and FACILITY_STORAGE.</span></span> <span data-ttu-id="28251-119">如果需要新的设施，Microsoft 会分配它们，因为它们需要是唯一的。</span><span class="sxs-lookup"><span data-stu-id="28251-119">If new facilities are necessary, Microsoft allocates them because they need to be unique.</span></span> <span data-ttu-id="28251-120">下表介绍了各种设施字段。</span><span class="sxs-lookup"><span data-stu-id="28251-120">The following table describes the various facility fields.</span></span>
  
|<span data-ttu-id="28251-121">设施</span><span class="sxs-lookup"><span data-stu-id="28251-121">Facility</span></span>|<span data-ttu-id="28251-122">说明</span><span class="sxs-lookup"><span data-stu-id="28251-122">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="28251-123">FACILITY_NULL</span><span class="sxs-lookup"><span data-stu-id="28251-123">FACILITY_NULL</span></span>  <br/> |<span data-ttu-id="28251-124">For broadly applicable common status codes such as S_OK or E_OUTOF_MEMORY;值为 0。</span><span class="sxs-lookup"><span data-stu-id="28251-124">For broadly applicable common status codes such as S_OK or E_OUTOF_MEMORY; the value is zero.</span></span>  <br/> |
|<span data-ttu-id="28251-125">FACILITY_ITF</span><span class="sxs-lookup"><span data-stu-id="28251-125">FACILITY_ITF</span></span>  <br/> |<span data-ttu-id="28251-126">对于大多数从接口方法返回的状态代码;值由 接口定义。</span><span class="sxs-lookup"><span data-stu-id="28251-126">For most status codes returned from interface methods; the value is defined by the interface.</span></span> <span data-ttu-id="28251-127">也就是说，两个 HRESULT 值与从两个不同接口返回的 32 位值完全相同，可能有不同的含义。</span><span class="sxs-lookup"><span data-stu-id="28251-127">That is, two HRESULT values with exactly the same 32-bit value returned from two different interfaces might have different meanings.</span></span>  <br/> |
|<span data-ttu-id="28251-128">FACILITY_DISPATCH</span><span class="sxs-lookup"><span data-stu-id="28251-128">FACILITY_DISPATCH</span></span>  <br/> |<span data-ttu-id="28251-129">对于晚期绑定 [IDispatch](https://msdn.microsoft.com/library/ms221608.aspx) 接口错误。</span><span class="sxs-lookup"><span data-stu-id="28251-129">For late binding [IDispatch](https://msdn.microsoft.com/library/ms221608.aspx) interface errors.</span></span>  <br/> |
|<span data-ttu-id="28251-130">FACILITY_RPC</span><span class="sxs-lookup"><span data-stu-id="28251-130">FACILITY_RPC</span></span>  <br/> |<span data-ttu-id="28251-131">对于从远程过程调用返回的状态代码。</span><span class="sxs-lookup"><span data-stu-id="28251-131">For status codes returned from remote procedure calls.</span></span>  <br/> |
|<span data-ttu-id="28251-132">FACILITY_STORAGE</span><span class="sxs-lookup"><span data-stu-id="28251-132">FACILITY_STORAGE</span></span>  <br/> |<span data-ttu-id="28251-133">对于从与结构化存储相关的 [IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx) 或 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 方法调用返回的状态代码。</span><span class="sxs-lookup"><span data-stu-id="28251-133">For status codes returned from [IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx) or [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) method calls relating to structured storage.</span></span> <span data-ttu-id="28251-134">代码小于 16 位 () 值的范围为 Windows 错误代码 (即小于 256) 与对应的 Windows 错误具有相同的含义。</span><span class="sxs-lookup"><span data-stu-id="28251-134">Status codes with code (lower 16 bits) values in the range of Windows error codes (that is, less than 256) have the same meaning as the corresponding Windows errors.</span></span>  <br/> |
   
<span data-ttu-id="28251-135">代码字段是分配用于表示错误或警告的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="28251-135">The code field is a unique number that is assigned to represent the error or warning.</span></span>
  

