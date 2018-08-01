---
title: IOlkAccountNotifyNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: dbce1c47-1252-ddeb-64ae-d52118e6821f
description: 通知客户端到指定的帐户的更改。
ms.openlocfilehash: ea4cab8cb8571cf5f34637c08935c78c657e5503
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774358"
---
# <a name="iolkaccountnotifynotify"></a><span data-ttu-id="891fc-103">IOlkAccountNotify::Notify</span><span class="sxs-lookup"><span data-stu-id="891fc-103">IOlkAccountNotify::Notify</span></span>

<span data-ttu-id="891fc-104">通知客户端到指定的帐户的更改。</span><span class="sxs-lookup"><span data-stu-id="891fc-104">Notifies the client of changes to the specified account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="891fc-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="891fc-105">Quick info</span></span>

<span data-ttu-id="891fc-106">请参阅[IOlkAccountNotify](iolkaccountnotify.md)。</span><span class="sxs-lookup"><span data-stu-id="891fc-106">See [IOlkAccountNotify](iolkaccountnotify.md).</span></span>
  
```cpp
HRESULT IOlkAccount::Notify(  
    DWORD dwNotify, 
    DWORD dwAcctID, 
    DWORD dwFlags 
);

```

## <a name="parameters"></a><span data-ttu-id="891fc-107">参数</span><span class="sxs-lookup"><span data-stu-id="891fc-107">Parameters</span></span>

<span data-ttu-id="891fc-108">_dwNotify_</span><span class="sxs-lookup"><span data-stu-id="891fc-108">_dwNotify_</span></span>
  
> <span data-ttu-id="891fc-109">[in]通知的类型。</span><span class="sxs-lookup"><span data-stu-id="891fc-109">[in] The type of notification.</span></span> <span data-ttu-id="891fc-110">该值必须为以下项之一：</span><span class="sxs-lookup"><span data-stu-id="891fc-110">The value must be one of the following:</span></span>
    
   - <span data-ttu-id="891fc-111">NOTIFY_ACCT_CHANGED</span><span class="sxs-lookup"><span data-stu-id="891fc-111">NOTIFY_ACCT_CHANGED</span></span> 
    
   - <span data-ttu-id="891fc-112">NOTIFY_ACCT_CREATED</span><span class="sxs-lookup"><span data-stu-id="891fc-112">NOTIFY_ACCT_CREATED</span></span> 
    
   - <span data-ttu-id="891fc-113">NOTIFY_ACCT_DELETED</span><span class="sxs-lookup"><span data-stu-id="891fc-113">NOTIFY_ACCT_DELETED</span></span>
    
   - <span data-ttu-id="891fc-114">NOTIFY_ACCT_ORDER_CHANGED</span><span class="sxs-lookup"><span data-stu-id="891fc-114">NOTIFY_ACCT_ORDER_CHANGED</span></span> 
    
   - <span data-ttu-id="891fc-115">NOTIFY_ACCT_PREDELETED</span><span class="sxs-lookup"><span data-stu-id="891fc-115">NOTIFY_ACCT_PREDELETED</span></span> 
    
 <span data-ttu-id="891fc-116">_dwAcctID_</span><span class="sxs-lookup"><span data-stu-id="891fc-116">_dwAcctID_</span></span>
  
> <span data-ttu-id="891fc-117">[in]已创建，更改的帐户的帐户 ID 删除，或者前删除。</span><span class="sxs-lookup"><span data-stu-id="891fc-117">[in] The account ID of the account that has been created, changed, deleted, or pre-deleted.</span></span>
    
 <span data-ttu-id="891fc-118">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="891fc-118">_dwFlags_</span></span>
  
>  <span data-ttu-id="891fc-119">[in]不使用。</span><span class="sxs-lookup"><span data-stu-id="891fc-119">[in] Not used.</span></span> <span data-ttu-id="891fc-120">OLK_ACCOUNT_NO_FLAGS 是唯一受支持的值。</span><span class="sxs-lookup"><span data-stu-id="891fc-120">OLK_ACCOUNT_NO_FLAGS is the only supported value.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="891fc-121">返回值</span><span class="sxs-lookup"><span data-stu-id="891fc-121">Return values</span></span>

<span data-ttu-id="891fc-122">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="891fc-122">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="891fc-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="891fc-123">See also</span></span>

- [<span data-ttu-id="891fc-124">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="891fc-124">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="891fc-125">IOlkAccountManager</span><span class="sxs-lookup"><span data-stu-id="891fc-125">IOlkAccountManager</span></span>](iolkaccountmanager.md)

