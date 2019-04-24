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
# <a name="error-handling-in-mapi"></a><span data-ttu-id="e802d-103">MAPI 中的错误处理</span><span class="sxs-lookup"><span data-stu-id="e802d-103">Error handling in MAPI</span></span>

<span data-ttu-id="e802d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e802d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e802d-105">成功、警告和错误值使用32位数字 (称为结果句柄) 或 HRESULT 返回。</span><span class="sxs-lookup"><span data-stu-id="e802d-105">Success, warning, and error values are returned using a 32-bit number known as a result handle, or HRESULT.</span></span> <span data-ttu-id="e802d-106">HRESULT 实际上不是任何一个句柄, 而是它只是一个32位值, 其中的多个字段编码在值中。</span><span class="sxs-lookup"><span data-stu-id="e802d-106">An HRESULT is really not a handle to anything; it is merely a 32-bit value with several fields encoded in the value.</span></span> <span data-ttu-id="e802d-107">零结果表示成功, 而非零结果表示失败。</span><span class="sxs-lookup"><span data-stu-id="e802d-107">A zero result indicates success and a nonzero result indicates failure.</span></span>
  
<span data-ttu-id="e802d-108">32位平台上的 MAPI 仅适用于 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="e802d-108">MAPI on 32-bit platforms works solely with HRESULT values.</span></span>
  
<span data-ttu-id="e802d-109">下图显示了32位平台的 HRESULT 格式。</span><span class="sxs-lookup"><span data-stu-id="e802d-109">The following illustration shows the HRESULT format for 32-bit platforms.</span></span>
  
<span data-ttu-id="e802d-110">**HRESULT 格式**</span><span class="sxs-lookup"><span data-stu-id="e802d-110">**HRESULT format**</span></span>
  
<span data-ttu-id="e802d-111">![HRESULT 格式](media/amapi_49.gif "HRESULT 格式")</span><span class="sxs-lookup"><span data-stu-id="e802d-111">![HRESULT format](media/amapi_49.gif "HRESULT format")</span></span>
  
<span data-ttu-id="e802d-112">HRESULT 中的 high order bit 指示返回值是表示成功还是失败。</span><span class="sxs-lookup"><span data-stu-id="e802d-112">The high order bit in the HRESULT indicates whether the return value represents success or failure.</span></span> <span data-ttu-id="e802d-113">如果设置为 0, 则该值表示 "成功"。</span><span class="sxs-lookup"><span data-stu-id="e802d-113">If set to zero, the value indicates success.</span></span> <span data-ttu-id="e802d-114">如果设置为 1, 则表示失败。</span><span class="sxs-lookup"><span data-stu-id="e802d-114">If set to 1, it indicates failure.</span></span>
  
<span data-ttu-id="e802d-115">在 HRESULT 中保留 r、C、N 和 r 位。</span><span class="sxs-lookup"><span data-stu-id="e802d-115">The R, C, N, and r bits are reserved in the HRESULT.</span></span>
  
<span data-ttu-id="e802d-116">这两个版本中的 "设施" 字段指示错误的职责范围。</span><span class="sxs-lookup"><span data-stu-id="e802d-116">The facility field in both versions indicates the area of responsibility for the error.</span></span> <span data-ttu-id="e802d-117">有几个功能, 但绝大多数 MAPI 错误都使用 FACILITY_ITF 表示接口错误。</span><span class="sxs-lookup"><span data-stu-id="e802d-117">There are several facilities, but the vast majority of MAPI errors use FACILITY_ITF to represent interface errors.</span></span> <span data-ttu-id="e802d-118">当前使用的最常见的功能是: FACILITY_NULL、FACILITY_ITF、FACILITY_DISPATCH、FACILITY_RPC 和 FACILITY_STORAGE。</span><span class="sxs-lookup"><span data-stu-id="e802d-118">The most common facilities that are currently used are: FACILITY_NULL, FACILITY_ITF, FACILITY_DISPATCH, FACILITY_RPC, and FACILITY_STORAGE.</span></span> <span data-ttu-id="e802d-119">如果需要新设备, Microsoft 会对其进行分配, 因为它们需要是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e802d-119">If new facilities are necessary, Microsoft allocates them because they need to be unique.</span></span> <span data-ttu-id="e802d-120">下表介绍了各种功能字段。</span><span class="sxs-lookup"><span data-stu-id="e802d-120">The following table describes the various facility fields.</span></span>
  
|<span data-ttu-id="e802d-121">设施</span><span class="sxs-lookup"><span data-stu-id="e802d-121">Facility</span></span>|<span data-ttu-id="e802d-122">说明</span><span class="sxs-lookup"><span data-stu-id="e802d-122">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="e802d-123">FACILITY_NULL</span><span class="sxs-lookup"><span data-stu-id="e802d-123">FACILITY_NULL</span></span>  <br/> |<span data-ttu-id="e802d-124">对于广泛适用的常见状态代码 (如 S_OK 或 E_OUTOF_MEMORY);值为零。</span><span class="sxs-lookup"><span data-stu-id="e802d-124">For broadly applicable common status codes such as S_OK or E_OUTOF_MEMORY; the value is zero.</span></span>  <br/> |
|<span data-ttu-id="e802d-125">FACILITY_ITF</span><span class="sxs-lookup"><span data-stu-id="e802d-125">FACILITY_ITF</span></span>  <br/> |<span data-ttu-id="e802d-126">对于从接口方法返回的大多数状态代码;该值由接口定义。</span><span class="sxs-lookup"><span data-stu-id="e802d-126">For most status codes returned from interface methods; the value is defined by the interface.</span></span> <span data-ttu-id="e802d-127">也就是说, 两个 HRESULT 值与从两个不同的接口返回的32位值完全相同可能具有不同的含义。</span><span class="sxs-lookup"><span data-stu-id="e802d-127">That is, two HRESULT values with exactly the same 32-bit value returned from two different interfaces might have different meanings.</span></span>  <br/> |
|<span data-ttu-id="e802d-128">FACILITY_DISPATCH</span><span class="sxs-lookup"><span data-stu-id="e802d-128">FACILITY_DISPATCH</span></span>  <br/> |<span data-ttu-id="e802d-129">对于后期绑定[IDispatch](https://msdn.microsoft.com/library/ms221608.aspx)接口错误。</span><span class="sxs-lookup"><span data-stu-id="e802d-129">For late binding [IDispatch](https://msdn.microsoft.com/library/ms221608.aspx) interface errors.</span></span>  <br/> |
|<span data-ttu-id="e802d-130">FACILITY_RPC</span><span class="sxs-lookup"><span data-stu-id="e802d-130">FACILITY_RPC</span></span>  <br/> |<span data-ttu-id="e802d-131">对于从远程过程调用返回的状态代码。</span><span class="sxs-lookup"><span data-stu-id="e802d-131">For status codes returned from remote procedure calls.</span></span>  <br/> |
|<span data-ttu-id="e802d-132">FACILITY_STORAGE</span><span class="sxs-lookup"><span data-stu-id="e802d-132">FACILITY_STORAGE</span></span>  <br/> |<span data-ttu-id="e802d-133">对于从[IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx)或与结构化存储相关的[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)方法调用返回的状态代码。</span><span class="sxs-lookup"><span data-stu-id="e802d-133">For status codes returned from [IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx) or [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) method calls relating to structured storage.</span></span> <span data-ttu-id="e802d-134">在 windows 错误代码范围 (即, 小于 256) 中包含代码的状态代码 (低16位) 值与对应的 Windows 错误具有相同的含义。</span><span class="sxs-lookup"><span data-stu-id="e802d-134">Status codes with code (lower 16 bits) values in the range of Windows error codes (that is, less than 256) have the same meaning as the corresponding Windows errors.</span></span>  <br/> |
   
<span data-ttu-id="e802d-135">"代码" 字段是分配给代表错误或警告的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="e802d-135">The code field is a unique number that is assigned to represent the error or warning.</span></span>
  

