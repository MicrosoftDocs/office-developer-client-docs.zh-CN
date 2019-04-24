---
title: IMAPISupportNewUID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.NewUID
api_type:
- COM
ms.assetid: 7994477d-5207-4335-b538-69c98782d52d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a38f7ea475f8a5cbad4f1cc295c3e2550ea8cd66
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330196"
---
# <a name="imapisupportnewuid"></a><span data-ttu-id="a5e94-103">IMAPISupport::NewUID</span><span class="sxs-lookup"><span data-stu-id="a5e94-103">IMAPISupport::NewUID</span></span>

  
  
<span data-ttu-id="a5e94-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a5e94-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a5e94-105">创建要用作唯一标识符的新[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="a5e94-105">Creates a new [MAPIUID](mapiuid.md) structure to be used as a unique identifier.</span></span> 
  
```cpp
HRESULT NewUID(
LPMAPIUID lpMuid
);
```

## <a name="parameters"></a><span data-ttu-id="a5e94-106">参数</span><span class="sxs-lookup"><span data-stu-id="a5e94-106">Parameters</span></span>

 <span data-ttu-id="a5e94-107">_lpMuid_</span><span class="sxs-lookup"><span data-stu-id="a5e94-107">_lpMuid_</span></span>
  
> <span data-ttu-id="a5e94-108">指向新的**MAPIUID**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="a5e94-108">A pointer to the new **MAPIUID** structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a5e94-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a5e94-109">Return value</span></span>

<span data-ttu-id="a5e94-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5e94-110">S_OK</span></span> 
  
> <span data-ttu-id="a5e94-111">已创建新的**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="a5e94-111">The new **MAPIUID** structure was created.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a5e94-112">注解</span><span class="sxs-lookup"><span data-stu-id="a5e94-112">Remarks</span></span>

<span data-ttu-id="a5e94-113">**IMAPISupport:: NewUID**方法是为所有支持对象实现的。</span><span class="sxs-lookup"><span data-stu-id="a5e94-113">The **IMAPISupport::NewUID** method is implemented for all support objects.</span></span> <span data-ttu-id="a5e94-114">每当服务提供程序和邮件服务需要生成长期唯一标识符时, 都会调用**NewUID** 。</span><span class="sxs-lookup"><span data-stu-id="a5e94-114">Service providers and message services call **NewUID** whenever they need to generate a long-term unique identifier.</span></span> <span data-ttu-id="a5e94-115">例如, 邮件存储提供程序可能会调用**NewUID**以获取**MAPIUID**以放置在新创建的邮件的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="a5e94-115">A message store provider, for example, might call **NewUID** to obtain a **MAPIUID** to put in the **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property of a newly created message.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="a5e94-116">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a5e94-116">Notes to callers</span></span>

<span data-ttu-id="a5e94-117">请勿将在登录时注册的**MAPIUID**结构与**NewUID**方法创建的**MAPIUID**结构相混淆。</span><span class="sxs-lookup"><span data-stu-id="a5e94-117">Do not confuse the **MAPIUID** structure that you register at logon time with the **MAPIUID** structures that the **NewUID** method creates.</span></span> <span data-ttu-id="a5e94-118">您在调用[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md)方法时注册的**MAPIUID**结构表示您的通讯簿或邮件存储提供程序到 MAPI, 用于区分不同提供程序创建的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a5e94-118">The **MAPIUID** structure that you register when you call the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method represents your address book or message store provider to MAPI and is used to distinguish entry identifiers that different providers create.</span></span> <span data-ttu-id="a5e94-119">此**MAPIUID**结构应是硬编码的, 不能通过调用**NewUID**获取。</span><span class="sxs-lookup"><span data-stu-id="a5e94-119">This **MAPIUID** structure should be hard-coded and not obtained through a call to **NewUID**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a5e94-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5e94-120">See also</span></span>



[<span data-ttu-id="a5e94-121">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="a5e94-121">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="a5e94-122">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a5e94-122">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

