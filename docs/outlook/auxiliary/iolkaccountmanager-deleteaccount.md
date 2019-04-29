---
title: IOlkAccountManagerDeleteAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: df210364-fe20-8e33-a455-9902f04ec739
description: 删除指定的帐户。
ms.openlocfilehash: 3e39b7b9af57f64dd124e1bf836db68664709b8c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431237"
---
# <a name="iolkaccountmanagerdeleteaccount"></a><span data-ttu-id="0bfd3-103">IOlkAccountManager::DeleteAccount</span><span class="sxs-lookup"><span data-stu-id="0bfd3-103">IOlkAccountManager::DeleteAccount</span></span>

<span data-ttu-id="0bfd3-104">删除指定的帐户。</span><span class="sxs-lookup"><span data-stu-id="0bfd3-104">Deletes the specified account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="0bfd3-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="0bfd3-105">Quick info</span></span>

<span data-ttu-id="0bfd3-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="0bfd3-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT IOlkAccountManager::DeleteAccount (  
    DWORD dwAcctID, 
);
```

## <a name="parameters"></a><span data-ttu-id="0bfd3-107">参数</span><span class="sxs-lookup"><span data-stu-id="0bfd3-107">Parameters</span></span>

<span data-ttu-id="0bfd3-108">_dwAcctID_</span><span class="sxs-lookup"><span data-stu-id="0bfd3-108">_dwAcctID_</span></span>
  
> <span data-ttu-id="0bfd3-109">实时要删除的帐户的帐户 ID。</span><span class="sxs-lookup"><span data-stu-id="0bfd3-109">[in] The account ID of the account to be deleted.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="0bfd3-110">返回值</span><span class="sxs-lookup"><span data-stu-id="0bfd3-110">Return values</span></span>

|<span data-ttu-id="0bfd3-111">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="0bfd3-111">**HRESULT**</span></span>|<span data-ttu-id="0bfd3-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="0bfd3-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0bfd3-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0bfd3-113">S_OK</span></span>  <br/> |<span data-ttu-id="0bfd3-114">呼叫成功</span><span class="sxs-lookup"><span data-stu-id="0bfd3-114">The call succeeded</span></span>  <br/> |
|<span data-ttu-id="0bfd3-115">E_ACCT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="0bfd3-115">E_ACCT_NOT_FOUND</span></span>  <br/> |<span data-ttu-id="0bfd3-116">找不到指定的帐户。</span><span class="sxs-lookup"><span data-stu-id="0bfd3-116">The specified account cannot be found.</span></span>  <br/> |
|<span data-ttu-id="0bfd3-117">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="0bfd3-117">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="0bfd3-118">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="0bfd3-118">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0bfd3-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bfd3-119">See also</span></span>

- [<span data-ttu-id="0bfd3-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="0bfd3-120">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="0bfd3-121">IOlkAccountManager::FindAccount</span><span class="sxs-lookup"><span data-stu-id="0bfd3-121">IOlkAccountManager::FindAccount</span></span>](iolkaccountmanager-findaccount.md)

