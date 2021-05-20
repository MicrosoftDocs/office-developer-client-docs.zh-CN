---
title: IMAPISupportSetProviderUID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.SetProviderUID
api_type:
- COM
ms.assetid: 58855843-9a2b-4e5d-9332-b1bfad8b45e4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a60ac0d7ab139f77aea87080e1ce37fee870e97b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437537"
---
# <a name="imapisupportsetprovideruid"></a><span data-ttu-id="d3b92-103">IMAPISupport::SetProviderUID</span><span class="sxs-lookup"><span data-stu-id="d3b92-103">IMAPISupport::SetProviderUID</span></span>

  
  
<span data-ttu-id="d3b92-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d3b92-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d3b92-105">注册一个唯一表示服务提供商的 [MAPIUID](mapiuid.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="d3b92-105">Registers a [MAPIUID](mapiuid.md) structure that uniquely represents the service provider.</span></span> 
  
```cpp
HRESULT SetProviderUID(
LPMAPIUID lpProviderID,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="d3b92-106">参数</span><span class="sxs-lookup"><span data-stu-id="d3b92-106">Parameters</span></span>

 <span data-ttu-id="d3b92-107">_lpProviderID_</span><span class="sxs-lookup"><span data-stu-id="d3b92-107">_lpProviderID_</span></span>
  
> <span data-ttu-id="d3b92-108">[in]指向标识通讯簿或邮件存储提供程序的 **MAPIUID** 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="d3b92-108">[in] A pointer to the **MAPIUID** structure that identifies the address book or message store provider.</span></span> 
    
 <span data-ttu-id="d3b92-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d3b92-109">_ulFlags_</span></span>
  
> <span data-ttu-id="d3b92-110">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="d3b92-110">Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d3b92-111">返回值</span><span class="sxs-lookup"><span data-stu-id="d3b92-111">Return value</span></span>

<span data-ttu-id="d3b92-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3b92-112">S_OK</span></span> 
  
> <span data-ttu-id="d3b92-113">**已成功注册 MAPIUID** 结构。</span><span class="sxs-lookup"><span data-stu-id="d3b92-113">The **MAPIUID** structure was successfully registered.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="d3b92-114">备注</span><span class="sxs-lookup"><span data-stu-id="d3b92-114">Remarks</span></span>

<span data-ttu-id="d3b92-115">**IMAPISupport：：SetProviderUID** 方法针对通讯簿和邮件存储提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="d3b92-115">The **IMAPISupport::SetProviderUID** method is implemented for address book and message store provider support objects.</span></span> <span data-ttu-id="d3b92-116">这些提供程序调用 **SetProviderUID** 以注册 **MAPIUID** 结构中描述的唯一标识符，该结构由  _lpProviderID 指向_。</span><span class="sxs-lookup"><span data-stu-id="d3b92-116">These providers call **SetProviderUID** to register a unique identifier described in the **MAPIUID** structure that is pointed to by  _lpProviderID_.</span></span> <span data-ttu-id="d3b92-117">提供程序在它们创建的所有条目标识符中包括此标识符。</span><span class="sxs-lookup"><span data-stu-id="d3b92-117">Providers include this identifier in all of the entry identifiers that they create.</span></span> 
  
<span data-ttu-id="d3b92-118">MAPI 在将出站邮件发送到 MAPI 后台处理程序并确定用于处理客户端请求的适当提供程序时，使用 **MAPIUID** 结构。</span><span class="sxs-lookup"><span data-stu-id="d3b92-118">MAPI uses the **MAPIUID** structure when it sends outbound messages to the MAPI spooler and to determine the appropriate provider for handling client requests.</span></span> <span data-ttu-id="d3b92-119">例如，当客户端调用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 方法时，MAPI 将检查条目标识符的 **MAPIUID** 部分，将 MAPIUID 部分映射到传递到 **SetProviderUID** 的提供程序，并调用该提供程序的 **OpenEntry**。</span><span class="sxs-lookup"><span data-stu-id="d3b92-119">For example, when a client calls the [IMAPISession::OpenEntry](imapisession-openentry.md) method, MAPI examines the **MAPIUID** portion of the entry identifier, maps it to the provider that passed it to **SetProviderUID**, and calls that provider's **OpenEntry**.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="d3b92-120">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d3b92-120">Notes to callers</span></span>

<span data-ttu-id="d3b92-121">在 **登录时调用 SetProviderUID** 以注册 **MAPIUID** 结构。</span><span class="sxs-lookup"><span data-stu-id="d3b92-121">Call **SetProviderUID** at logon time to register your **MAPIUID** structure.</span></span> <span data-ttu-id="d3b92-122">MAPI 允许通讯簿和邮件存储提供程序注册多个标识符。</span><span class="sxs-lookup"><span data-stu-id="d3b92-122">MAPI allows address book and message store providers to register multiple identifiers.</span></span> <span data-ttu-id="d3b92-123">当您多次调用 **SetProviderUID** 时，它始终会将 **MAPIUID** 结构添加到提供程序的 **MAPIUID** 结构集，即使 **MAPIUID** 是重复的。</span><span class="sxs-lookup"><span data-stu-id="d3b92-123">When you make multiple calls to **SetProviderUID**, it always adds the **MAPIUID** structure to the provider's set of **MAPIUID** structures, even if the **MAPIUID** is a duplicate.</span></span> <span data-ttu-id="d3b92-124">**SetProviderUID** 无法删除 **MAPIUID**。</span><span class="sxs-lookup"><span data-stu-id="d3b92-124">**SetProviderUID** cannot remove a **MAPIUID**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d3b92-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3b92-125">See also</span></span>



[<span data-ttu-id="d3b92-126">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="d3b92-126">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="d3b92-127">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d3b92-127">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

