---
title: IOlkAccountNotifyNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: dbce1c47-1252-ddeb-64ae-d52118e6821f
description: 通知客户端对指定帐户的更改。
ms.openlocfilehash: 269d8a8bd605c9d8a0a4057e87895522d8587ee9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424565"
---
# <a name="iolkaccountnotifynotify"></a><span data-ttu-id="5a95a-103">IOlkAccountNotify::Notify</span><span class="sxs-lookup"><span data-stu-id="5a95a-103">IOlkAccountNotify::Notify</span></span>

<span data-ttu-id="5a95a-104">通知客户端对指定帐户的更改。</span><span class="sxs-lookup"><span data-stu-id="5a95a-104">Notifies the client of changes to the specified account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5a95a-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="5a95a-105">Quick info</span></span>

<span data-ttu-id="5a95a-106">请参阅 [IOlkAccountNotify](iolkaccountnotify.md)。</span><span class="sxs-lookup"><span data-stu-id="5a95a-106">See [IOlkAccountNotify](iolkaccountnotify.md).</span></span>
  
```cpp
HRESULT IOlkAccount::Notify(  
    DWORD dwNotify, 
    DWORD dwAcctID, 
    DWORD dwFlags 
);

```

## <a name="parameters"></a><span data-ttu-id="5a95a-107">参数</span><span class="sxs-lookup"><span data-stu-id="5a95a-107">Parameters</span></span>

<span data-ttu-id="5a95a-108">_dwNotify_</span><span class="sxs-lookup"><span data-stu-id="5a95a-108">_dwNotify_</span></span>
  
> <span data-ttu-id="5a95a-109">[in]通知的类型。</span><span class="sxs-lookup"><span data-stu-id="5a95a-109">[in] The type of notification.</span></span> <span data-ttu-id="5a95a-110">值必须为以下值之一：</span><span class="sxs-lookup"><span data-stu-id="5a95a-110">The value must be one of the following:</span></span>
    
   - <span data-ttu-id="5a95a-111">NOTIFY_ACCT_CHANGED</span><span class="sxs-lookup"><span data-stu-id="5a95a-111">NOTIFY_ACCT_CHANGED</span></span> 
    
   - <span data-ttu-id="5a95a-112">NOTIFY_ACCT_CREATED</span><span class="sxs-lookup"><span data-stu-id="5a95a-112">NOTIFY_ACCT_CREATED</span></span> 
    
   - <span data-ttu-id="5a95a-113">NOTIFY_ACCT_DELETED</span><span class="sxs-lookup"><span data-stu-id="5a95a-113">NOTIFY_ACCT_DELETED</span></span>
    
   - <span data-ttu-id="5a95a-114">NOTIFY_ACCT_ORDER_CHANGED</span><span class="sxs-lookup"><span data-stu-id="5a95a-114">NOTIFY_ACCT_ORDER_CHANGED</span></span> 
    
   - <span data-ttu-id="5a95a-115">NOTIFY_ACCT_PREDELETED</span><span class="sxs-lookup"><span data-stu-id="5a95a-115">NOTIFY_ACCT_PREDELETED</span></span> 
    
 <span data-ttu-id="5a95a-116">_dwAcctID_</span><span class="sxs-lookup"><span data-stu-id="5a95a-116">_dwAcctID_</span></span>
  
> <span data-ttu-id="5a95a-117">[in]已创建、更改、删除或预删除的帐户的帐户 ID。</span><span class="sxs-lookup"><span data-stu-id="5a95a-117">[in] The account ID of the account that has been created, changed, deleted, or pre-deleted.</span></span>
    
 <span data-ttu-id="5a95a-118">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="5a95a-118">_dwFlags_</span></span>
  
>  <span data-ttu-id="5a95a-119">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="5a95a-119">[in] Not used.</span></span> <span data-ttu-id="5a95a-120">OLK_ACCOUNT_NO_FLAGS是唯一受支持的值。</span><span class="sxs-lookup"><span data-stu-id="5a95a-120">OLK_ACCOUNT_NO_FLAGS is the only supported value.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="5a95a-121">返回值</span><span class="sxs-lookup"><span data-stu-id="5a95a-121">Return values</span></span>

<span data-ttu-id="5a95a-122">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="5a95a-122">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5a95a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a95a-123">See also</span></span>

- [<span data-ttu-id="5a95a-124">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="5a95a-124">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="5a95a-125">IOlkAccountManager</span><span class="sxs-lookup"><span data-stu-id="5a95a-125">IOlkAccountManager</span></span>](iolkaccountmanager.md)

