---
title: IOlkAccountManagerInit
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0e5ffb61-1469-bc91-f237-27d1156179cd
description: 初始化的程序使用的帐户管理器。
ms.openlocfilehash: 621c6a73ab2bcbdff17b87ce15af8b4e0c2e1e24
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774335"
---
# <a name="iolkaccountmanagerinit"></a><span data-ttu-id="8cf09-103">IOlkAccountManager::Init</span><span class="sxs-lookup"><span data-stu-id="8cf09-103">IOlkAccountManager::Init</span></span>

<span data-ttu-id="8cf09-104">初始化的程序使用的帐户管理器。</span><span class="sxs-lookup"><span data-stu-id="8cf09-104">Initializes the account manager for use.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="8cf09-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="8cf09-105">Quick info</span></span>

<span data-ttu-id="8cf09-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="8cf09-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT IOlkAccountManager::Init (  
    IOlkAccountHelper *pAcctHelper, 
    DWORD dwFlags 
);

```

## <a name="parameters"></a><span data-ttu-id="8cf09-107">参数</span><span class="sxs-lookup"><span data-stu-id="8cf09-107">Parameters</span></span>

<span data-ttu-id="8cf09-108">_pAcctHelper_</span><span class="sxs-lookup"><span data-stu-id="8cf09-108">_pAcctHelper_</span></span>
  
> <span data-ttu-id="8cf09-109">[in][IOlkAccountHelper](iolkaccounthelper.md)接口提供帐户帮助程序功能。</span><span class="sxs-lookup"><span data-stu-id="8cf09-109">[in] An [IOlkAccountHelper](iolkaccounthelper.md) interface that provides account helper functionality.</span></span> 
    
<span data-ttu-id="8cf09-110">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="8cf09-110">_dwFlags_</span></span>
  
> <span data-ttu-id="8cf09-111">[] in若要修改行为的标志。</span><span class="sxs-lookup"><span data-stu-id="8cf09-111">[in] Flags to modify behavior.</span></span>
    
   - <span data-ttu-id="8cf09-112">**ACCT_INIT_NO_STORES_CHECK** — 防止与相关联的存储进行同步的帐户 （例如 IMAP 帐户）。</span><span class="sxs-lookup"><span data-stu-id="8cf09-112">**ACCT_INIT_NO_STORES_CHECK** —Prevents an account (such as an IMAP account) from synchronizing with an associated store.</span></span> 
    
   - <span data-ttu-id="8cf09-113">**ACCT_INIT_NOSYNCH_MAPI_ACCTS** — 阻止 MAPI 服务帐户与同步。</span><span class="sxs-lookup"><span data-stu-id="8cf09-113">**ACCT_INIT_NOSYNCH_MAPI_ACCTS** —Prevents MAPI services from synchronizing with accounts.</span></span> 
    
   - <span data-ttu-id="8cf09-114">**OLK_ACCOUNT_NO_FLAGS** — 同步 MAPI 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="8cf09-114">**OLK_ACCOUNT_NO_FLAGS** —Synchronizes MAPI services with accounts.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="8cf09-115">返回值</span><span class="sxs-lookup"><span data-stu-id="8cf09-115">Return values</span></span>

|<span data-ttu-id="8cf09-116">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="8cf09-116">**HRESULT**</span></span>|<span data-ttu-id="8cf09-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="8cf09-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8cf09-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="8cf09-118">S_OK</span></span>  <br/> |<span data-ttu-id="8cf09-119">调用成功。</span><span class="sxs-lookup"><span data-stu-id="8cf09-119">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="8cf09-120">E_OLK_ALREADY_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="8cf09-120">E_OLK_ALREADY_INITIALIZED</span></span>  <br/> |<span data-ttu-id="8cf09-121">已调用**Init** 。</span><span class="sxs-lookup"><span data-stu-id="8cf09-121">**Init** has already been called.</span></span>  <br/> |
|<span data-ttu-id="8cf09-122">E_OLK_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="8cf09-122">E_OLK_REGISTRY</span></span>  <br/> |<span data-ttu-id="8cf09-123">帐户管理器无法访问所需的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="8cf09-123">The account manager could not access the required registry settings.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8cf09-124">说明</span><span class="sxs-lookup"><span data-stu-id="8cf09-124">Remarks</span></span>

<span data-ttu-id="8cf09-125">客户端之前必须调用**IOlkAccountManager::Init**初始化帐户管理器使用的帐户管理器可以访问帐户或设置通知。</span><span class="sxs-lookup"><span data-stu-id="8cf09-125">The client must call **IOlkAccountManager::Init** to initialize the account manager before using the account manager to access accounts or set up notifications.</span></span> <span data-ttu-id="8cf09-126">由于 Outlook 自动同步 MAPI 服务在启动时的帐户，使用**ACCT_INIT_NOSYNCH_MAPI_ACCTS** ，除非有具体原因同步。</span><span class="sxs-lookup"><span data-stu-id="8cf09-126">Because Outlook automatically synchronizes MAPI services with accounts on startup, use **ACCT_INIT_NOSYNCH_MAPI_ACCTS** unless there is a specific cause to synchronize.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8cf09-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cf09-127">See also</span></span>

- [<span data-ttu-id="8cf09-128">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="8cf09-128">Constants (Account management API)</span></span>](constants-account-management-api.md)

