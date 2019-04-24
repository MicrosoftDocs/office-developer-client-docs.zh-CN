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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327214"
---
# <a name="strategies-for-error-handling"></a><span data-ttu-id="eb43b-103">错误处理策略</span><span class="sxs-lookup"><span data-stu-id="eb43b-103">Strategies for Error Handling</span></span>

  
  
<span data-ttu-id="eb43b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eb43b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eb43b-105">由于接口方法是虚拟的, 因此不可能知道可从任何一个调用返回的完整值集。</span><span class="sxs-lookup"><span data-stu-id="eb43b-105">Because interface methods are virtual, it is not possible to know, as a caller, the full set of values that can be returned from any one call.</span></span> <span data-ttu-id="eb43b-106">方法的一个实现可能返回5个值;另一个可能返回8个。</span><span class="sxs-lookup"><span data-stu-id="eb43b-106">One implementation of a method might return five values; another might return eight.</span></span> <span data-ttu-id="eb43b-107">MAPI 文档列表中的引用条目可为每个方法返回几个值;您的客户端或服务提供商可以对其进行检查和处理的值, 因为它们具有特殊含义。</span><span class="sxs-lookup"><span data-stu-id="eb43b-107">The reference entries in the MAPI documentation list a few values that can be returned for each method; these are the values that your client or service provider can check for and handle because they have special meanings.</span></span> <span data-ttu-id="eb43b-108">可以返回其他值, 但由于它们没有意义, 因此处理这些值的特殊代码不是必需的。</span><span class="sxs-lookup"><span data-stu-id="eb43b-108">Other values can be returned, but because they are not meaningful, special code to handle those is not necessary.</span></span> <span data-ttu-id="eb43b-109">成功或失败的简单检查就足够了。</span><span class="sxs-lookup"><span data-stu-id="eb43b-109">A simple check for success or failure is adequate.</span></span>
  
<span data-ttu-id="eb43b-110">几种接口方法返回警告。</span><span class="sxs-lookup"><span data-stu-id="eb43b-110">A few of the interface methods return warnings.</span></span> <span data-ttu-id="eb43b-111">如果您的客户端或服务提供商调用的方法可以返回警告, 请使用**HR_FAILED**宏来测试返回值, 而不是检查是否为零或非零。</span><span class="sxs-lookup"><span data-stu-id="eb43b-111">If a method that your client or service provider calls can return a warning, use the **HR_FAILED** macro to test the return value rather than a check for zero or nonzero.</span></span> <span data-ttu-id="eb43b-112">警告 (尽管非零) 与错误代码的不同之处在于, 它们没有设置高位。</span><span class="sxs-lookup"><span data-stu-id="eb43b-112">Warnings, although nonzero, differ from error codes in that they do not have the high bit set.</span></span> <span data-ttu-id="eb43b-113">如果您的客户端或服务提供商不使用宏, 可能会有警告被误认为失败。</span><span class="sxs-lookup"><span data-stu-id="eb43b-113">If your client or service provider does not use the macro, it is likely that a warning might be mistaken for a failure.</span></span> 
  
<span data-ttu-id="eb43b-114">尽管大多数接口方法和函数都返回 HRESULT 值, 但某些函数会返回无符号的 long 值。</span><span class="sxs-lookup"><span data-stu-id="eb43b-114">Although most interface methods and functions return HRESULT values, some functions return unsigned long values.</span></span> <span data-ttu-id="eb43b-115">此外, MAPI 环境中使用的某些方法来自 com, 并返回 com 错误值, 而不是 MAPI 错误值。</span><span class="sxs-lookup"><span data-stu-id="eb43b-115">Also, some methods used in the MAPI environment come from COM and return COM error values rather than MAPI error values.</span></span> <span data-ttu-id="eb43b-116">调用时请牢记以下准则:</span><span class="sxs-lookup"><span data-stu-id="eb43b-116">Keep in mind the following guidelines when making calls:</span></span>
  
- <span data-ttu-id="eb43b-117">从不依赖或使用来自**IUnknown:: AddRef**或**iunknown:: Release**的返回值。</span><span class="sxs-lookup"><span data-stu-id="eb43b-117">Never rely on or use the return values from **IUnknown::AddRef** or **IUnknown::Release**.</span></span> <span data-ttu-id="eb43b-118">这些返回值仅用于诊断目的。</span><span class="sxs-lookup"><span data-stu-id="eb43b-118">These return values are for diagnostic purposes only.</span></span> 
    
- <span data-ttu-id="eb43b-119">**IUnknown:: QueryInterface**总是返回常规 COM 错误, 其中设备为 FACILITY_NULL 或 FACILITY_RPC, 而不是 MAPI 错误。</span><span class="sxs-lookup"><span data-stu-id="eb43b-119">**IUnknown::QueryInterface** always returns generic COM errors where the facility is FACILITY_NULL or FACILITY_RPC, rather than MAPI errors.</span></span> 
    
- <span data-ttu-id="eb43b-120">所有其他接口方法返回的 MAPI 接口错误与 FACILITY_ITF 或 FACILITY_RPC 或 FACILITY_NULL 错误的功能。</span><span class="sxs-lookup"><span data-stu-id="eb43b-120">All other interface methods return MAPI interface errors with a facility of FACILITY_ITF, or FACILITY_RPC or FACILITY_NULL errors.</span></span>
    
<span data-ttu-id="eb43b-121">当调用不受支持的 MAPI 方法时, 可能会返回以下四个错误之一:</span><span class="sxs-lookup"><span data-stu-id="eb43b-121">When a call is made to an unsupported MAPI method, one of four possible errors can be returned:</span></span> 
  
<span data-ttu-id="eb43b-122">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="eb43b-122">MAPI_E_NO_SUPPORT</span></span>
  
<span data-ttu-id="eb43b-123">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="eb43b-123">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span>
  
<span data-ttu-id="eb43b-124">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="eb43b-124">MAPI_E_INVALID_PARAMETER</span></span>
  
<span data-ttu-id="eb43b-125">MAPI_E_VERSION。</span><span class="sxs-lookup"><span data-stu-id="eb43b-125">MAPI_E_VERSION.</span></span> 
  

