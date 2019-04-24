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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326311"
---
# <a name="imapisupportsetprovideruid"></a><span data-ttu-id="9c617-103">IMAPISupport::SetProviderUID</span><span class="sxs-lookup"><span data-stu-id="9c617-103">IMAPISupport::SetProviderUID</span></span>

  
  
<span data-ttu-id="9c617-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9c617-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9c617-105">注册唯一表示服务提供程序的[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="9c617-105">Registers a [MAPIUID](mapiuid.md) structure that uniquely represents the service provider.</span></span> 
  
```cpp
HRESULT SetProviderUID(
LPMAPIUID lpProviderID,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="9c617-106">参数</span><span class="sxs-lookup"><span data-stu-id="9c617-106">Parameters</span></span>

 <span data-ttu-id="9c617-107">_lpProviderID_</span><span class="sxs-lookup"><span data-stu-id="9c617-107">_lpProviderID_</span></span>
  
> <span data-ttu-id="9c617-108">实时指向标识通讯簿或邮件存储提供程序的**MAPIUID**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="9c617-108">[in] A pointer to the **MAPIUID** structure that identifies the address book or message store provider.</span></span> 
    
 <span data-ttu-id="9c617-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9c617-109">_ulFlags_</span></span>
  
> <span data-ttu-id="9c617-110">保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="9c617-110">Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9c617-111">返回值</span><span class="sxs-lookup"><span data-stu-id="9c617-111">Return value</span></span>

<span data-ttu-id="9c617-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c617-112">S_OK</span></span> 
  
> <span data-ttu-id="9c617-113">已成功注册**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="9c617-113">The **MAPIUID** structure was successfully registered.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="9c617-114">注解</span><span class="sxs-lookup"><span data-stu-id="9c617-114">Remarks</span></span>

<span data-ttu-id="9c617-115">为通讯簿和邮件存储提供程序支持对象实现了**IMAPISupport:: SetProviderUID**方法。</span><span class="sxs-lookup"><span data-stu-id="9c617-115">The **IMAPISupport::SetProviderUID** method is implemented for address book and message store provider support objects.</span></span> <span data-ttu-id="9c617-116">这些提供程序调用**SetProviderUID**以注册_lpProviderID_指向的**MAPIUID**结构中描述的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="9c617-116">These providers call **SetProviderUID** to register a unique identifier described in the **MAPIUID** structure that is pointed to by  _lpProviderID_.</span></span> <span data-ttu-id="9c617-117">提供程序在其创建的所有条目标识符中都包含此标识符。</span><span class="sxs-lookup"><span data-stu-id="9c617-117">Providers include this identifier in all of the entry identifiers that they create.</span></span> 
  
<span data-ttu-id="9c617-118">mapi 在向 mapi 后台处理程序发送出站邮件时使用**MAPIUID**结构, 并确定处理客户端请求的适当提供程序。</span><span class="sxs-lookup"><span data-stu-id="9c617-118">MAPI uses the **MAPIUID** structure when it sends outbound messages to the MAPI spooler and to determine the appropriate provider for handling client requests.</span></span> <span data-ttu-id="9c617-119">例如, 当客户端调用[IMAPISession:: OpenEntry](imapisession-openentry.md)方法时, MAPI 会检查条目标识符的**MAPIUID**部分, 将其映射到传递给**SetProviderUID**的提供程序, 并调用该提供程序的**OpenEntry**.</span><span class="sxs-lookup"><span data-stu-id="9c617-119">For example, when a client calls the [IMAPISession::OpenEntry](imapisession-openentry.md) method, MAPI examines the **MAPIUID** portion of the entry identifier, maps it to the provider that passed it to **SetProviderUID**, and calls that provider's **OpenEntry**.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="9c617-120">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9c617-120">Notes to callers</span></span>

<span data-ttu-id="9c617-121">在登录时调用**SetProviderUID**以注册**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="9c617-121">Call **SetProviderUID** at logon time to register your **MAPIUID** structure.</span></span> <span data-ttu-id="9c617-122">MAPI 允许通讯簿和邮件存储提供程序注册多个标识符。</span><span class="sxs-lookup"><span data-stu-id="9c617-122">MAPI allows address book and message store providers to register multiple identifiers.</span></span> <span data-ttu-id="9c617-123">当您对**SetProviderUID**进行多次调用时, 它始终会将**MAPIUID**结构添加到提供程序的**MAPIUID**结构集, 即使**MAPIUID**是重复的也是如此。</span><span class="sxs-lookup"><span data-stu-id="9c617-123">When you make multiple calls to **SetProviderUID**, it always adds the **MAPIUID** structure to the provider's set of **MAPIUID** structures, even if the **MAPIUID** is a duplicate.</span></span> <span data-ttu-id="9c617-124">**SetProviderUID**无法删除**MAPIUID**。</span><span class="sxs-lookup"><span data-stu-id="9c617-124">**SetProviderUID** cannot remove a **MAPIUID**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9c617-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c617-125">See also</span></span>



[<span data-ttu-id="9c617-126">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="9c617-126">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="9c617-127">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9c617-127">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

