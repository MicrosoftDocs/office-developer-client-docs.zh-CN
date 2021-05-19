---
title: IOlkAccountManagerAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c88f087e-4ff4-0837-186d-b6e761468a4d
description: 向帐户管理员注册客户端，以接收有关所有帐户的通知。
ms.openlocfilehash: 5460d55d906d382ce40ecd3fd9277cf370295680
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427708"
---
# <a name="iolkaccountmanageradvise"></a><span data-ttu-id="d469a-103">IOlkAccountManager::Advise</span><span class="sxs-lookup"><span data-stu-id="d469a-103">IOlkAccountManager::Advise</span></span>

<span data-ttu-id="d469a-104">向帐户管理员注册客户端，以接收有关所有帐户的通知。</span><span class="sxs-lookup"><span data-stu-id="d469a-104">Registers a client with the account manager for notifications regarding all accounts.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d469a-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="d469a-105">Quick info</span></span>

<span data-ttu-id="d469a-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="d469a-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT IOlkAccountManager::Advise (  
    IOlkAccountNotify *pNotify, 
    DWORD *pdwCookie 
);
```

## <a name="parameters"></a><span data-ttu-id="d469a-107">参数</span><span class="sxs-lookup"><span data-stu-id="d469a-107">Parameters</span></span>

<span data-ttu-id="d469a-108">_pNotify_</span><span class="sxs-lookup"><span data-stu-id="d469a-108">_pNotify_</span></span>
  
> <span data-ttu-id="d469a-109">[in]帐户管理员用于向客户端发送通知的 [IOlkAccountNotify](iolkaccountnotify.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="d469a-109">[in] An [IOlkAccountNotify](iolkaccountnotify.md) interface that the account manager will use to send notifications to the client.</span></span> 
    
<span data-ttu-id="d469a-110">_pdwCookie_</span><span class="sxs-lookup"><span data-stu-id="d469a-110">_pdwCookie_</span></span>
  
> <span data-ttu-id="d469a-111">[out] [IOlkAccountManager：：Unadvise](iolkaccountmanager-unadvise.md) 在删除帐户注册时将使用的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="d469a-111">[out] A cookie that [IOlkAccountManager::Unadvise](iolkaccountmanager-unadvise.md) will use when removing the registration for the account.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="d469a-112">返回值</span><span class="sxs-lookup"><span data-stu-id="d469a-112">Return values</span></span>

|<span data-ttu-id="d469a-113">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="d469a-113">**HRESULT**</span></span>|<span data-ttu-id="d469a-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="d469a-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d469a-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d469a-115">S_OK</span></span>  <br/> |<span data-ttu-id="d469a-116">调用成功。</span><span class="sxs-lookup"><span data-stu-id="d469a-116">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="d469a-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d469a-117">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="d469a-118">提供了无效的参数。</span><span class="sxs-lookup"><span data-stu-id="d469a-118">An invalid argument has been provided.</span></span>  <br/> |
|<span data-ttu-id="d469a-119">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="d469a-119">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="d469a-120">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="d469a-120">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d469a-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d469a-121">See also</span></span>

- [<span data-ttu-id="d469a-122">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="d469a-122">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="d469a-123">IOlkAccountManager::Unadvise</span><span class="sxs-lookup"><span data-stu-id="d469a-123">IOlkAccountManager::Unadvise</span></span>](iolkaccountmanager-unadvise.md)

