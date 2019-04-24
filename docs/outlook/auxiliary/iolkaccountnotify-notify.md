---
title: IOlkAccountNotifyNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: dbce1c47-1252-ddeb-64ae-d52118e6821f
description: 通知客户端对指定帐户所做的更改。
ms.openlocfilehash: 269d8a8bd605c9d8a0a4057e87895522d8587ee9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321964"
---
# <a name="iolkaccountnotifynotify"></a><span data-ttu-id="88bf2-103">IOlkAccountNotify::Notify</span><span class="sxs-lookup"><span data-stu-id="88bf2-103">IOlkAccountNotify::Notify</span></span>

<span data-ttu-id="88bf2-104">通知客户端对指定帐户所做的更改。</span><span class="sxs-lookup"><span data-stu-id="88bf2-104">Notifies the client of changes to the specified account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="88bf2-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="88bf2-105">Quick info</span></span>

<span data-ttu-id="88bf2-106">请参阅[IOlkAccountNotify](iolkaccountnotify.md)。</span><span class="sxs-lookup"><span data-stu-id="88bf2-106">See [IOlkAccountNotify](iolkaccountnotify.md).</span></span>
  
```cpp
HRESULT IOlkAccount::Notify(  
    DWORD dwNotify, 
    DWORD dwAcctID, 
    DWORD dwFlags 
);

```

## <a name="parameters"></a><span data-ttu-id="88bf2-107">参数</span><span class="sxs-lookup"><span data-stu-id="88bf2-107">Parameters</span></span>

<span data-ttu-id="88bf2-108">_dwNotify_</span><span class="sxs-lookup"><span data-stu-id="88bf2-108">_dwNotify_</span></span>
  
> <span data-ttu-id="88bf2-109">实时通知的类型。</span><span class="sxs-lookup"><span data-stu-id="88bf2-109">[in] The type of notification.</span></span> <span data-ttu-id="88bf2-110">值必须为以下值之一：</span><span class="sxs-lookup"><span data-stu-id="88bf2-110">The value must be one of the following:</span></span>
    
   - <span data-ttu-id="88bf2-111">NOTIFY_ACCT_CHANGED</span><span class="sxs-lookup"><span data-stu-id="88bf2-111">NOTIFY_ACCT_CHANGED</span></span> 
    
   - <span data-ttu-id="88bf2-112">NOTIFY_ACCT_CREATED</span><span class="sxs-lookup"><span data-stu-id="88bf2-112">NOTIFY_ACCT_CREATED</span></span> 
    
   - <span data-ttu-id="88bf2-113">NOTIFY_ACCT_DELETED</span><span class="sxs-lookup"><span data-stu-id="88bf2-113">NOTIFY_ACCT_DELETED</span></span>
    
   - <span data-ttu-id="88bf2-114">NOTIFY_ACCT_ORDER_CHANGED</span><span class="sxs-lookup"><span data-stu-id="88bf2-114">NOTIFY_ACCT_ORDER_CHANGED</span></span> 
    
   - <span data-ttu-id="88bf2-115">NOTIFY_ACCT_PREDELETED</span><span class="sxs-lookup"><span data-stu-id="88bf2-115">NOTIFY_ACCT_PREDELETED</span></span> 
    
 <span data-ttu-id="88bf2-116">_dwAcctID_</span><span class="sxs-lookup"><span data-stu-id="88bf2-116">_dwAcctID_</span></span>
  
> <span data-ttu-id="88bf2-117">实时已创建、更改、删除或预删除的帐户的帐户 ID。</span><span class="sxs-lookup"><span data-stu-id="88bf2-117">[in] The account ID of the account that has been created, changed, deleted, or pre-deleted.</span></span>
    
 <span data-ttu-id="88bf2-118">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="88bf2-118">_dwFlags_</span></span>
  
>  <span data-ttu-id="88bf2-119">实时不使用。</span><span class="sxs-lookup"><span data-stu-id="88bf2-119">[in] Not used.</span></span> <span data-ttu-id="88bf2-120">OLK_ACCOUNT_NO_FLAGS 是唯一受支持的值。</span><span class="sxs-lookup"><span data-stu-id="88bf2-120">OLK_ACCOUNT_NO_FLAGS is the only supported value.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="88bf2-121">返回值</span><span class="sxs-lookup"><span data-stu-id="88bf2-121">Return values</span></span>

<span data-ttu-id="88bf2-122">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="88bf2-122">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="88bf2-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88bf2-123">See also</span></span>

- [<span data-ttu-id="88bf2-124">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="88bf2-124">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="88bf2-125">IOlkAccountManager</span><span class="sxs-lookup"><span data-stu-id="88bf2-125">IOlkAccountManager</span></span>](iolkaccountmanager.md)

