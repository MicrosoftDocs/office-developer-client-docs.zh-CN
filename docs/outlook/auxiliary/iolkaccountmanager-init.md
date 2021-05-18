---
title: IOlkAccountManagerInit
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0e5ffb61-1469-bc91-f237-27d1156179cd
description: 初始化帐户管理器以使用。
ms.openlocfilehash: 5a643a4636251afc98750be8acf47cd3bdab3847
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322034"
---
# <a name="iolkaccountmanagerinit"></a><span data-ttu-id="76067-103">IOlkAccountManager::Init</span><span class="sxs-lookup"><span data-stu-id="76067-103">IOlkAccountManager::Init</span></span>

<span data-ttu-id="76067-104">初始化帐户管理器以使用。</span><span class="sxs-lookup"><span data-stu-id="76067-104">Initializes the account manager for use.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="76067-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="76067-105">Quick info</span></span>

<span data-ttu-id="76067-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="76067-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT IOlkAccountManager::Init (  
    IOlkAccountHelper *pAcctHelper, 
    DWORD dwFlags 
);

```

## <a name="parameters"></a><span data-ttu-id="76067-107">参数</span><span class="sxs-lookup"><span data-stu-id="76067-107">Parameters</span></span>

<span data-ttu-id="76067-108">_pAcctHelper_</span><span class="sxs-lookup"><span data-stu-id="76067-108">_pAcctHelper_</span></span>
  
> <span data-ttu-id="76067-109">[in]提供 [帐户帮助程序功能的 IOlkAccountHelper](iolkaccounthelper.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="76067-109">[in] An [IOlkAccountHelper](iolkaccounthelper.md) interface that provides account helper functionality.</span></span> 
    
<span data-ttu-id="76067-110">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="76067-110">_dwFlags_</span></span>
  
> <span data-ttu-id="76067-111">[] in若要修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="76067-111">[in] Flags to modify behavior.</span></span>
    
   - <span data-ttu-id="76067-112">**ACCT_INIT_NO_STORES_CHECK** — 阻止 (IMAP 帐户等) 与关联存储同步。</span><span class="sxs-lookup"><span data-stu-id="76067-112">**ACCT_INIT_NO_STORES_CHECK** —Prevents an account (such as an IMAP account) from synchronizing with an associated store.</span></span> 
    
   - <span data-ttu-id="76067-113">**ACCT_INIT_NOSYNCH_MAPI_ACCTS** - 阻止 MAPI 服务与帐户同步。</span><span class="sxs-lookup"><span data-stu-id="76067-113">**ACCT_INIT_NOSYNCH_MAPI_ACCTS** —Prevents MAPI services from synchronizing with accounts.</span></span> 
   
   - <span data-ttu-id="76067-114">**ACCT_INIT_NO_NOTIFICATIONS** — 阻止帐户管理器截获用于其他应用程序的广播消息。</span><span class="sxs-lookup"><span data-stu-id="76067-114">**ACCT_INIT_NO_NOTIFICATIONS** —Prevents the Account Manager from intercepting broadcast messages intended for other applications.</span></span> 
   
   - <span data-ttu-id="76067-115">**OLK_ACCOUNT_NO_FLAGS** - 将 MAPI 服务与帐户同步。</span><span class="sxs-lookup"><span data-stu-id="76067-115">**OLK_ACCOUNT_NO_FLAGS** —Synchronizes MAPI services with accounts.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="76067-116">返回值</span><span class="sxs-lookup"><span data-stu-id="76067-116">Return values</span></span>

|<span data-ttu-id="76067-117">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="76067-117">**HRESULT**</span></span>|<span data-ttu-id="76067-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="76067-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="76067-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="76067-119">S_OK</span></span>  <br/> |<span data-ttu-id="76067-120">调用成功。</span><span class="sxs-lookup"><span data-stu-id="76067-120">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="76067-121">E_OLK_ALREADY_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="76067-121">E_OLK_ALREADY_INITIALIZED</span></span>  <br/> |<span data-ttu-id="76067-122">**已调用 Init。**</span><span class="sxs-lookup"><span data-stu-id="76067-122">**Init** has already been called.</span></span>  <br/> |
|<span data-ttu-id="76067-123">E_OLK_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="76067-123">E_OLK_REGISTRY</span></span>  <br/> |<span data-ttu-id="76067-124">帐户管理员无法访问所需的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="76067-124">The account manager could not access the required registry settings.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="76067-125">备注</span><span class="sxs-lookup"><span data-stu-id="76067-125">Remarks</span></span>

<span data-ttu-id="76067-126">客户端必须先调用 **IOlkAccountManager：：Init** 以初始化帐户管理器，然后才能使用帐户管理器访问帐户或设置通知。</span><span class="sxs-lookup"><span data-stu-id="76067-126">The client must call **IOlkAccountManager::Init** to initialize the account manager before using the account manager to access accounts or set up notifications.</span></span> <span data-ttu-id="76067-127">由于Outlook时会自动将 MAPI 服务与帐户同步，ACCT_INIT_NOSYNCH_MAPI_ACCTS，除非有特定原因需要同步。</span><span class="sxs-lookup"><span data-stu-id="76067-127">Because Outlook automatically synchronizes MAPI services with accounts on startup, use **ACCT_INIT_NOSYNCH_MAPI_ACCTS** unless there is a specific cause to synchronize.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="76067-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76067-128">See also</span></span>

- [<span data-ttu-id="76067-129">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="76067-129">Constants (Account management API)</span></span>](constants-account-management-api.md)

