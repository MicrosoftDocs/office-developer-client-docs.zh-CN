---
title: IOlkAccountManagerUnadvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea5cbf9f-25cc-9cca-9be0-d2deed576153
description: 使用帐户管理器注销客户端，以通知所有帐户。
ms.openlocfilehash: 0b954413b06cb1aa1b6fc4e0e9666f108bf81fbe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430985"
---
# <a name="iolkaccountmanagerunadvise"></a><span data-ttu-id="4d817-103">IOlkAccountManager::Unadvise</span><span class="sxs-lookup"><span data-stu-id="4d817-103">IOlkAccountManager::Unadvise</span></span>

<span data-ttu-id="4d817-104">使用帐户管理器注销客户端，以通知所有帐户。</span><span class="sxs-lookup"><span data-stu-id="4d817-104">Unregisters a client with the account manager for notifications for all accounts.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="4d817-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="4d817-105">Quick info</span></span>

<span data-ttu-id="4d817-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="4d817-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT Unadvise(
    DWORD dwCookie
);

```

## <a name="parameters"></a><span data-ttu-id="4d817-107">参数</span><span class="sxs-lookup"><span data-stu-id="4d817-107">Parameters</span></span>

<span data-ttu-id="4d817-108">_dwCookie_</span><span class="sxs-lookup"><span data-stu-id="4d817-108">_dwCookie_</span></span>
  
> <span data-ttu-id="4d817-109">[in][IOlkAccountManager：：Advise 返回的 Cookie。](iolkaccountmanager-advise.md)</span><span class="sxs-lookup"><span data-stu-id="4d817-109">[in] The cookie returned by [IOlkAccountManager::Advise](iolkaccountmanager-advise.md).</span></span>
    
## <a name="return-values"></a><span data-ttu-id="4d817-110">返回值</span><span class="sxs-lookup"><span data-stu-id="4d817-110">Return values</span></span>

|<span data-ttu-id="4d817-111">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="4d817-111">**HRESULT**</span></span>|<span data-ttu-id="4d817-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="4d817-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d817-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d817-113">S_OK</span></span>  <br/> |<span data-ttu-id="4d817-114">调用成功。</span><span class="sxs-lookup"><span data-stu-id="4d817-114">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="4d817-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4d817-115">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="4d817-116">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="4d817-116">One or more arguments are invalid.</span></span>  <br/> |
|<span data-ttu-id="4d817-117">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="4d817-117">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="4d817-118">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="4d817-118">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4d817-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d817-119">See also</span></span>

- [<span data-ttu-id="4d817-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="4d817-120">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="4d817-121">IOlkAccountManager::Advise</span><span class="sxs-lookup"><span data-stu-id="4d817-121">IOlkAccountManager::Advise</span></span>](iolkaccountmanager-advise.md)

