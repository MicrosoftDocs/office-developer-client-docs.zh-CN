---
title: IOlkAccountManagerAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c88f087e-4ff4-0837-186d-b6e761468a4d
description: 有关所有帐户的通知帐户管理器中注册的客户端。
ms.openlocfilehash: 1fb697fef44b9ed32888527c3c9e467be69ba4c7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774331"
---
# <a name="iolkaccountmanageradvise"></a><span data-ttu-id="bded4-103">IOlkAccountManager::Advise</span><span class="sxs-lookup"><span data-stu-id="bded4-103">IOlkAccountManager::Advise</span></span>

<span data-ttu-id="bded4-104">有关所有帐户的通知帐户管理器中注册的客户端。</span><span class="sxs-lookup"><span data-stu-id="bded4-104">Registers a client with the account manager for notifications regarding all accounts.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="bded4-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="bded4-105">Quick info</span></span>

<span data-ttu-id="bded4-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="bded4-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT IOlkAccountManager::Advise (  
    IOlkAccountNotify *pNotify, 
    DWORD *pdwCookie 
);
```

## <a name="parameters"></a><span data-ttu-id="bded4-107">参数</span><span class="sxs-lookup"><span data-stu-id="bded4-107">Parameters</span></span>

<span data-ttu-id="bded4-108">_pNotify_</span><span class="sxs-lookup"><span data-stu-id="bded4-108">_pNotify_</span></span>
  
> <span data-ttu-id="bded4-109">[in]帐户管理器将用于将通知发送到客户端[IOlkAccountNotify](iolkaccountnotify.md)接口。</span><span class="sxs-lookup"><span data-stu-id="bded4-109">[in] An [IOlkAccountNotify](iolkaccountnotify.md) interface that the account manager will use to send notifications to the client.</span></span> 
    
<span data-ttu-id="bded4-110">_pdwCookie_</span><span class="sxs-lookup"><span data-stu-id="bded4-110">_pdwCookie_</span></span>
  
> <span data-ttu-id="bded4-111">[输出]删除帐户注册时，将使用[IOlkAccountManager::Unadvise](iolkaccountmanager-unadvise.md) cookie。</span><span class="sxs-lookup"><span data-stu-id="bded4-111">[out] A cookie that [IOlkAccountManager::Unadvise](iolkaccountmanager-unadvise.md) will use when removing the registration for the account.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="bded4-112">返回值</span><span class="sxs-lookup"><span data-stu-id="bded4-112">Return values</span></span>

|<span data-ttu-id="bded4-113">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="bded4-113">**HRESULT**</span></span>|<span data-ttu-id="bded4-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="bded4-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bded4-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="bded4-115">S_OK</span></span>  <br/> |<span data-ttu-id="bded4-116">调用成功。</span><span class="sxs-lookup"><span data-stu-id="bded4-116">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="bded4-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bded4-117">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="bded4-118">已提供了无效的参数。</span><span class="sxs-lookup"><span data-stu-id="bded4-118">An invalid argument has been provided.</span></span>  <br/> |
|<span data-ttu-id="bded4-119">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="bded4-119">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="bded4-120">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="bded4-120">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bded4-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bded4-121">See also</span></span>

- [<span data-ttu-id="bded4-122">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="bded4-122">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="bded4-123">IOlkAccountManager::Unadvise</span><span class="sxs-lookup"><span data-stu-id="bded4-123">IOlkAccountManager::Unadvise</span></span>](iolkaccountmanager-unadvise.md)

