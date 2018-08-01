---
title: IOlkAccountManagerUnadvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea5cbf9f-25cc-9cca-9be0-d2deed576153
description: 取消注册的所有帐户的通知帐户管理器客户端。
ms.openlocfilehash: 0632bc6bd98e218cf323262ea480b020185438f3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774347"
---
# <a name="iolkaccountmanagerunadvise"></a><span data-ttu-id="2f3bf-103">IOlkAccountManager::Unadvise</span><span class="sxs-lookup"><span data-stu-id="2f3bf-103">IOlkAccountManager::Unadvise</span></span>

<span data-ttu-id="2f3bf-104">取消注册的所有帐户的通知帐户管理器客户端。</span><span class="sxs-lookup"><span data-stu-id="2f3bf-104">Unregisters a client with the account manager for notifications for all accounts.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="2f3bf-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="2f3bf-105">Quick info</span></span>

<span data-ttu-id="2f3bf-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="2f3bf-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT Unadvise(
    DWORD dwCookie
);

```

## <a name="parameters"></a><span data-ttu-id="2f3bf-107">参数</span><span class="sxs-lookup"><span data-stu-id="2f3bf-107">Parameters</span></span>

<span data-ttu-id="2f3bf-108">_dwCookie_</span><span class="sxs-lookup"><span data-stu-id="2f3bf-108">_dwCookie_</span></span>
  
> <span data-ttu-id="2f3bf-109">[in]返回[IOlkAccountManager::Advise](iolkaccountmanager-advise.md)cookie。</span><span class="sxs-lookup"><span data-stu-id="2f3bf-109">[in] The cookie returned by [IOlkAccountManager::Advise](iolkaccountmanager-advise.md).</span></span>
    
## <a name="return-values"></a><span data-ttu-id="2f3bf-110">返回值</span><span class="sxs-lookup"><span data-stu-id="2f3bf-110">Return values</span></span>

|<span data-ttu-id="2f3bf-111">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="2f3bf-111">**HRESULT**</span></span>|<span data-ttu-id="2f3bf-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="2f3bf-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2f3bf-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f3bf-113">S_OK</span></span>  <br/> |<span data-ttu-id="2f3bf-114">调用成功。</span><span class="sxs-lookup"><span data-stu-id="2f3bf-114">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="2f3bf-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2f3bf-115">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="2f3bf-116">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="2f3bf-116">One or more arguments are invalid.</span></span>  <br/> |
|<span data-ttu-id="2f3bf-117">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="2f3bf-117">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="2f3bf-118">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="2f3bf-118">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2f3bf-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f3bf-119">See also</span></span>

- [<span data-ttu-id="2f3bf-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="2f3bf-120">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="2f3bf-121">IOlkAccountManager::Advise</span><span class="sxs-lookup"><span data-stu-id="2f3bf-121">IOlkAccountManager::Advise</span></span>](iolkaccountmanager-advise.md)

