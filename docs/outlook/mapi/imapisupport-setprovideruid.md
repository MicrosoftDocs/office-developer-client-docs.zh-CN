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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2182ec71c54c81e9a43a34973e005292ddccdfff
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775661"
---
# <a name="imapisupportsetprovideruid"></a><span data-ttu-id="06c0b-103">IMAPISupport::SetProviderUID</span><span class="sxs-lookup"><span data-stu-id="06c0b-103">IMAPISupport::SetProviderUID</span></span>

  
  
<span data-ttu-id="06c0b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="06c0b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="06c0b-105">注册[MAPIUID](mapiuid.md)结构，它唯一表示服务提供商。</span><span class="sxs-lookup"><span data-stu-id="06c0b-105">Registers a [MAPIUID](mapiuid.md) structure that uniquely represents the service provider.</span></span> 
  
```cpp
HRESULT SetProviderUID(
LPMAPIUID lpProviderID,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="06c0b-106">参数</span><span class="sxs-lookup"><span data-stu-id="06c0b-106">Parameters</span></span>

 <span data-ttu-id="06c0b-107">_lpProviderID_</span><span class="sxs-lookup"><span data-stu-id="06c0b-107">_lpProviderID_</span></span>
  
> <span data-ttu-id="06c0b-108">[in]指向标识的通讯簿或消息存储提供程序的**MAPIUID**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="06c0b-108">[in] A pointer to the **MAPIUID** structure that identifies the address book or message store provider.</span></span> 
    
 <span data-ttu-id="06c0b-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="06c0b-109">_ulFlags_</span></span>
  
> <span data-ttu-id="06c0b-110">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="06c0b-110">Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="06c0b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="06c0b-111">Return value</span></span>

<span data-ttu-id="06c0b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="06c0b-112">S_OK</span></span> 
  
> <span data-ttu-id="06c0b-113">已成功注册**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="06c0b-113">The **MAPIUID** structure was successfully registered.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="06c0b-114">说明</span><span class="sxs-lookup"><span data-stu-id="06c0b-114">Remarks</span></span>

<span data-ttu-id="06c0b-115">对于通讯簿和消息存储提供程序支持对象实现**IMAPISupport::SetProviderUID**方法。</span><span class="sxs-lookup"><span data-stu-id="06c0b-115">The **IMAPISupport::SetProviderUID** method is implemented for address book and message store provider support objects.</span></span> <span data-ttu-id="06c0b-116">这些提供程序调用**SetProviderUID**注册_lpProviderID_所指向的**MAPIUID**结构中所述的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="06c0b-116">These providers call **SetProviderUID** to register a unique identifier described in the **MAPIUID** structure that is pointed to by  _lpProviderID_.</span></span> <span data-ttu-id="06c0b-117">提供程序中的项标识符为他们创建的所有包含此标识符。</span><span class="sxs-lookup"><span data-stu-id="06c0b-117">Providers include this identifier in all of the entry identifiers that they create.</span></span> 
  
<span data-ttu-id="06c0b-118">MAPI 到 MAPI 后台处理程序并确定相应的提供程序，用于处理客户端请求发送出站邮件时使用的**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="06c0b-118">MAPI uses the **MAPIUID** structure when it sends outbound messages to the MAPI spooler and to determine the appropriate provider for handling client requests.</span></span> <span data-ttu-id="06c0b-119">例如，当客户端调用[IMAPISession::OpenEntry](imapisession-openentry.md)方法，则 MAPI 将检查的项标识符的**MAPIUID**部分，将其映射到传递给**SetProviderUID**，并调用该提供商的**OpenEntry**的提供程序.</span><span class="sxs-lookup"><span data-stu-id="06c0b-119">For example, when a client calls the [IMAPISession::OpenEntry](imapisession-openentry.md) method, MAPI examines the **MAPIUID** portion of the entry identifier, maps it to the provider that passed it to **SetProviderUID**, and calls that provider's **OpenEntry**.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="06c0b-120">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="06c0b-120">Notes to callers</span></span>

<span data-ttu-id="06c0b-121">在登录时，若要注册**MAPIUID**结构调用**SetProviderUID** 。</span><span class="sxs-lookup"><span data-stu-id="06c0b-121">Call **SetProviderUID** at logon time to register your **MAPIUID** structure.</span></span> <span data-ttu-id="06c0b-122">MAPI 允许通讯簿和消息存储提供程序注册多个标识符。</span><span class="sxs-lookup"><span data-stu-id="06c0b-122">MAPI allows address book and message store providers to register multiple identifiers.</span></span> <span data-ttu-id="06c0b-123">当您进行多次调用**SetProviderUID**时，它始终向**MAPIUID**结构**MAPIUID**结构的提供程序的设置即使**MAPIUID**副本。</span><span class="sxs-lookup"><span data-stu-id="06c0b-123">When you make multiple calls to **SetProviderUID**, it always adds the **MAPIUID** structure to the provider's set of **MAPIUID** structures, even if the **MAPIUID** is a duplicate.</span></span> <span data-ttu-id="06c0b-124">**SetProviderUID**不能删除**MAPIUID**。</span><span class="sxs-lookup"><span data-stu-id="06c0b-124">**SetProviderUID** cannot remove a **MAPIUID**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="06c0b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06c0b-125">See also</span></span>



[<span data-ttu-id="06c0b-126">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="06c0b-126">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="06c0b-127">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="06c0b-127">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

