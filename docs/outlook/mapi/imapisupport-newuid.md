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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 244087c41e33e470c42434e9d57cee7317bcb78c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571687"
---
# <a name="imapisupportnewuid"></a><span data-ttu-id="45014-103">IMAPISupport::NewUID</span><span class="sxs-lookup"><span data-stu-id="45014-103">IMAPISupport::NewUID</span></span>

  
  
<span data-ttu-id="45014-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="45014-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="45014-105">创建一个新的[MAPIUID](mapiuid.md)结构用作唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="45014-105">Creates a new [MAPIUID](mapiuid.md) structure to be used as a unique identifier.</span></span> 
  
```cpp
HRESULT NewUID(
LPMAPIUID lpMuid
);
```

## <a name="parameters"></a><span data-ttu-id="45014-106">参数</span><span class="sxs-lookup"><span data-stu-id="45014-106">Parameters</span></span>

 <span data-ttu-id="45014-107">_lpMuid_</span><span class="sxs-lookup"><span data-stu-id="45014-107">_lpMuid_</span></span>
  
> <span data-ttu-id="45014-108">指向新**MAPIUID**结构的指针。</span><span class="sxs-lookup"><span data-stu-id="45014-108">A pointer to the new **MAPIUID** structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="45014-109">返回值</span><span class="sxs-lookup"><span data-stu-id="45014-109">Return value</span></span>

<span data-ttu-id="45014-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="45014-110">S_OK</span></span> 
  
> <span data-ttu-id="45014-111">创建新的**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="45014-111">The new **MAPIUID** structure was created.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="45014-112">注解</span><span class="sxs-lookup"><span data-stu-id="45014-112">Remarks</span></span>

<span data-ttu-id="45014-113">对于所有支持对象实现**IMAPISupport::NewUID**方法。</span><span class="sxs-lookup"><span data-stu-id="45014-113">The **IMAPISupport::NewUID** method is implemented for all support objects.</span></span> <span data-ttu-id="45014-114">服务提供商和消息服务调用**NewUID** ，只要他们需要生成的长期的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="45014-114">Service providers and message services call **NewUID** whenever they need to generate a long-term unique identifier.</span></span> <span data-ttu-id="45014-115">消息存储提供程序，例如，可能会调用**NewUID**获取**MAPIUID**将放入新创建的消息的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="45014-115">A message store provider, for example, might call **NewUID** to obtain a **MAPIUID** to put in the **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property of a newly created message.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="45014-116">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="45014-116">Notes to callers</span></span>

<span data-ttu-id="45014-117">请勿将在登录时与**NewUID**方法创建的**MAPIUID**结构注册**MAPIUID**结构混淆。</span><span class="sxs-lookup"><span data-stu-id="45014-117">Do not confuse the **MAPIUID** structure that you register at logon time with the **MAPIUID** structures that the **NewUID** method creates.</span></span> <span data-ttu-id="45014-118">注册调用[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)方法时**MAPIUID**结构表示通讯簿或消息存储到 MAPI 提供程序和用于区分不同的提供程序创建的项标识符。</span><span class="sxs-lookup"><span data-stu-id="45014-118">The **MAPIUID** structure that you register when you call the [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md) method represents your address book or message store provider to MAPI and is used to distinguish entry identifiers that different providers create.</span></span> <span data-ttu-id="45014-119">此**MAPIUID**结构应硬编码，并通过**NewUID**调用未获得。</span><span class="sxs-lookup"><span data-stu-id="45014-119">This **MAPIUID** structure should be hard-coded and not obtained through a call to **NewUID**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="45014-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45014-120">See also</span></span>



[<span data-ttu-id="45014-121">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="45014-121">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="45014-122">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="45014-122">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

