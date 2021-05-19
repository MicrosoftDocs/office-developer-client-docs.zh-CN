---
title: 错误处理策略
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: be941efd-04b3-48d0-9b9c-8195ad2bb58d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9e76ae3f292d8348b9dc64cb54bffae96b96e871
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424145"
---
# <a name="strategies-for-error-handling"></a><span data-ttu-id="3c9cf-103">错误处理策略</span><span class="sxs-lookup"><span data-stu-id="3c9cf-103">Strategies for Error Handling</span></span>

  
  
<span data-ttu-id="3c9cf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3c9cf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3c9cf-105">由于接口方法是虚拟的，因此作为调用方，无法知道可以从任何一个调用返回的完整值集。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-105">Because interface methods are virtual, it is not possible to know, as a caller, the full set of values that can be returned from any one call.</span></span> <span data-ttu-id="3c9cf-106">方法的一个实现可能返回五个值;另一个可能返回 8。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-106">One implementation of a method might return five values; another might return eight.</span></span> <span data-ttu-id="3c9cf-107">MAPI 文档中的参考条目列出了可以针对每个方法返回的一些值;这些是客户端或服务提供商可以检查和处理的值，因为它们具有特殊的含义。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-107">The reference entries in the MAPI documentation list a few values that can be returned for each method; these are the values that your client or service provider can check for and handle because they have special meanings.</span></span> <span data-ttu-id="3c9cf-108">可以返回其他值，但由于这些值没有意义，因此不需要处理这些值的特殊代码。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-108">Other values can be returned, but because they are not meaningful, special code to handle those is not necessary.</span></span> <span data-ttu-id="3c9cf-109">只需简单检查成功还是失败就足够了。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-109">A simple check for success or failure is adequate.</span></span>
  
<span data-ttu-id="3c9cf-110">一些接口方法返回警告。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-110">A few of the interface methods return warnings.</span></span> <span data-ttu-id="3c9cf-111">如果客户端或服务提供商调用的方法可以返回警告，请使用 HR_FAILED 宏来测试返回值，而不是检查返回值是零还是非零。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-111">If a method that your client or service provider calls can return a warning, use the **HR_FAILED** macro to test the return value rather than a check for zero or nonzero.</span></span> <span data-ttu-id="3c9cf-112">警告虽然不是零，但不同于错误代码，因为它们没有设置高位。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-112">Warnings, although nonzero, differ from error codes in that they do not have the high bit set.</span></span> <span data-ttu-id="3c9cf-113">如果您的客户端或服务提供商不使用该宏，则可能会因为失败而错误地显示一条警告。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-113">If your client or service provider does not use the macro, it is likely that a warning might be mistaken for a failure.</span></span> 
  
<span data-ttu-id="3c9cf-114">虽然大多数接口方法和函数都返回 HRESULT 值，但某些函数返回无符号长数值。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-114">Although most interface methods and functions return HRESULT values, some functions return unsigned long values.</span></span> <span data-ttu-id="3c9cf-115">此外，MAPI 环境中使用某些方法来自 COM 并返回 COM 错误值，而不是 MAPI 错误值。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-115">Also, some methods used in the MAPI environment come from COM and return COM error values rather than MAPI error values.</span></span> <span data-ttu-id="3c9cf-116">进行呼叫时，请记住以下准则：</span><span class="sxs-lookup"><span data-stu-id="3c9cf-116">Keep in mind the following guidelines when making calls:</span></span>
  
- <span data-ttu-id="3c9cf-117">绝不依赖或使用 **IUnknown：：AddRef** 或 **IUnknown：：Release 中的返回值**。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-117">Never rely on or use the return values from **IUnknown::AddRef** or **IUnknown::Release**.</span></span> <span data-ttu-id="3c9cf-118">这些返回值仅供诊断使用。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-118">These return values are for diagnostic purposes only.</span></span> 
    
- <span data-ttu-id="3c9cf-119">**IUnknown：：QueryInterface** 始终返回常规 COM 错误，其中设备是FACILITY_NULL或FACILITY_RPC，而不是 MAPI 错误。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-119">**IUnknown::QueryInterface** always returns generic COM errors where the facility is FACILITY_NULL or FACILITY_RPC, rather than MAPI errors.</span></span> 
    
- <span data-ttu-id="3c9cf-120">所有其他接口方法都返回 MAPI 接口错误，这些接口FACILITY_ITF或FACILITY_RPC或FACILITY_NULL错误。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-120">All other interface methods return MAPI interface errors with a facility of FACILITY_ITF, or FACILITY_RPC or FACILITY_NULL errors.</span></span>
    
<span data-ttu-id="3c9cf-121">当调用不受支持的 MAPI 方法时，可能会返回以下四个可能的错误之一：</span><span class="sxs-lookup"><span data-stu-id="3c9cf-121">When a call is made to an unsupported MAPI method, one of four possible errors can be returned:</span></span> 
  
<span data-ttu-id="3c9cf-122">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="3c9cf-122">MAPI_E_NO_SUPPORT</span></span>
  
<span data-ttu-id="3c9cf-123">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="3c9cf-123">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span>
  
<span data-ttu-id="3c9cf-124">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="3c9cf-124">MAPI_E_INVALID_PARAMETER</span></span>
  
<span data-ttu-id="3c9cf-125">MAPI_E_VERSION。</span><span class="sxs-lookup"><span data-stu-id="3c9cf-125">MAPI_E_VERSION.</span></span> 
  

