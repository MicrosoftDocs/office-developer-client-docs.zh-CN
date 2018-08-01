---
title: IOlkAccountManagerDeleteAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: df210364-fe20-8e33-a455-9902f04ec739
description: 删除指定的帐户。
ms.openlocfilehash: 1c0b246af10dac1af9c61f368d082a92c7b3616a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774339"
---
# <a name="iolkaccountmanagerdeleteaccount"></a><span data-ttu-id="d5512-103">IOlkAccountManager::DeleteAccount</span><span class="sxs-lookup"><span data-stu-id="d5512-103">IOlkAccountManager::DeleteAccount</span></span>

<span data-ttu-id="d5512-104">删除指定的帐户。</span><span class="sxs-lookup"><span data-stu-id="d5512-104">Deletes the specified account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d5512-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="d5512-105">Quick info</span></span>

<span data-ttu-id="d5512-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="d5512-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
```cpp
HRESULT IOlkAccountManager::DeleteAccount (  
    DWORD dwAcctID, 
);
```

## <a name="parameters"></a><span data-ttu-id="d5512-107">参数</span><span class="sxs-lookup"><span data-stu-id="d5512-107">Parameters</span></span>

<span data-ttu-id="d5512-108">_dwAcctID_</span><span class="sxs-lookup"><span data-stu-id="d5512-108">_dwAcctID_</span></span>
  
> <span data-ttu-id="d5512-109">[in]要删除帐户的帐户 ID。</span><span class="sxs-lookup"><span data-stu-id="d5512-109">[in] The account ID of the account to be deleted.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="d5512-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d5512-110">Return values</span></span>

|<span data-ttu-id="d5512-111">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="d5512-111">**HRESULT**</span></span>|<span data-ttu-id="d5512-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="d5512-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d5512-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5512-113">S_OK</span></span>  <br/> |<span data-ttu-id="d5512-114">成功呼叫</span><span class="sxs-lookup"><span data-stu-id="d5512-114">The call succeeded</span></span>  <br/> |
|<span data-ttu-id="d5512-115">E_ACCT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="d5512-115">E_ACCT_NOT_FOUND</span></span>  <br/> |<span data-ttu-id="d5512-116">找不到指定的帐户。</span><span class="sxs-lookup"><span data-stu-id="d5512-116">The specified account cannot be found.</span></span>  <br/> |
|<span data-ttu-id="d5512-117">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="d5512-117">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="d5512-118">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="d5512-118">The account manager has not been initialized for use.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d5512-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5512-119">See also</span></span>

- [<span data-ttu-id="d5512-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="d5512-120">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="d5512-121">IOlkAccountManager::FindAccount</span><span class="sxs-lookup"><span data-stu-id="d5512-121">IOlkAccountManager::FindAccount</span></span>](iolkaccountmanager-findaccount.md)

