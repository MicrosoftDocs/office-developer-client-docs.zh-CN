---
title: 用于错误处理的策略
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: be941efd-04b3-48d0-9b9c-8195ad2bb58d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e778df216d0fe9b901cd9f7136c8014a6b8f0d0a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778883"
---
# <a name="strategies-for-error-handling"></a><span data-ttu-id="7ca9e-103">用于错误处理的策略</span><span class="sxs-lookup"><span data-stu-id="7ca9e-103">Strategies for Error Handling</span></span>

  
  
<span data-ttu-id="7ca9e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7ca9e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7ca9e-105">由于接口方法是虚拟，不能为呼叫者，了解整套可以从任何一个的调用返回的值。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-105">Because interface methods are virtual, it is not possible to know, as a caller, the full set of values that can be returned from any one call.</span></span> <span data-ttu-id="7ca9e-106">一种方法的实现可能返回五个值;另一个可能返回 8。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-106">One implementation of a method might return five values; another might return eight.</span></span> <span data-ttu-id="7ca9e-107">MAPI 文档中的引用条目列表几个可针对每种方法; 返回的值这些是您的客户端或服务提供商可以检查和处理，因为它们具有特殊含义的值。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-107">The reference entries in the MAPI documentation list a few values that can be returned for each method; these are the values that your client or service provider can check for and handle because they have special meanings.</span></span> <span data-ttu-id="7ca9e-108">可返回其他值，但因为它们不是有意义，特殊代码以处理那些没有必要。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-108">Other values can be returned, but because they are not meaningful, special code to handle those is not necessary.</span></span> <span data-ttu-id="7ca9e-109">对成功或失败的简单检查就足够了。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-109">A simple check for success or failure is adequate.</span></span>
  
<span data-ttu-id="7ca9e-110">几个接口方法返回的警告。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-110">A few of the interface methods return warnings.</span></span> <span data-ttu-id="7ca9e-111">如果您的客户端或服务提供商调用的方法可返回一条警告，请使用**HR_FAILED**宏测试的返回值，而不是零或非零值的检查。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-111">If a method that your client or service provider calls can return a warning, use the **HR_FAILED** macro to test the return value rather than a check for zero or nonzero.</span></span> <span data-ttu-id="7ca9e-112">警告，虽然非零值，不同错误代码，它们不具有较高的位设置。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-112">Warnings, although nonzero, differ from error codes in that they do not have the high bit set.</span></span> <span data-ttu-id="7ca9e-113">如果您的客户端或服务提供程序不使用宏，很可能的可能失败的错误警告。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-113">If your client or service provider does not use the macro, it is likely that a warning might be mistaken for a failure.</span></span> 
  
<span data-ttu-id="7ca9e-114">尽管大多数接口方法和函数返回 HRESULT 值，但某些函数将返回未签署的长整型值。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-114">Although most interface methods and functions return HRESULT values, some functions return unsigned long values.</span></span> <span data-ttu-id="7ca9e-115">此外，MAPI 环境中使用某些方法来自 COM，并返回 COM 错误值，而不是 MAPI 错误值。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-115">Also, some methods used in the MAPI environment come from COM and return COM error values rather than MAPI error values.</span></span> <span data-ttu-id="7ca9e-116">发出呼叫时，请记住以下准则：</span><span class="sxs-lookup"><span data-stu-id="7ca9e-116">Keep in mind the following guidelines when making calls:</span></span>
  
- <span data-ttu-id="7ca9e-117">不要依赖或使用从**IUnknown::AddRef**或**IUnknown::Release**的返回值。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-117">Never rely on or use the return values from **IUnknown::AddRef** or **IUnknown::Release**.</span></span> <span data-ttu-id="7ca9e-118">这些返回值是仅用于诊断。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-118">These return values are for diagnostic purposes only.</span></span> 
    
- <span data-ttu-id="7ca9e-119">**IUnknown::QueryInterface**始终返回其中实用工具是 FACILITY_NULL 或 FACILITY_RPC，一般的 COM 错误，而不是 MAPI 错误。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-119">**IUnknown::QueryInterface** always returns generic COM errors where the facility is FACILITY_NULL or FACILITY_RPC, rather than MAPI errors.</span></span> 
    
- <span data-ttu-id="7ca9e-120">所有其他接口方法返回与 FACILITY_ITF 或 FACILITY_RPC 的设施 MAPI 界面错误或 FACILITY_NULL 错误。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-120">All other interface methods return MAPI interface errors with a facility of FACILITY_ITF, or FACILITY_RPC or FACILITY_NULL errors.</span></span>
    
<span data-ttu-id="7ca9e-121">时调用了不受支持的 MAPI 方法，可返回四个可能的错误之一：</span><span class="sxs-lookup"><span data-stu-id="7ca9e-121">When a call is made to an unsupported MAPI method, one of four possible errors can be returned:</span></span> 
  
<span data-ttu-id="7ca9e-122">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="7ca9e-122">MAPI_E_NO_SUPPORT</span></span>
  
<span data-ttu-id="7ca9e-123">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="7ca9e-123">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span>
  
<span data-ttu-id="7ca9e-124">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="7ca9e-124">MAPI_E_INVALID_PARAMETER</span></span>
  
<span data-ttu-id="7ca9e-125">MAPI_E_VERSION。</span><span class="sxs-lookup"><span data-stu-id="7ca9e-125">MAPI_E_VERSION.</span></span> 
  

