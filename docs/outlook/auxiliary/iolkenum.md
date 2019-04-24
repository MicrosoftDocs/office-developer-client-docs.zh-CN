---
title: IOlkEnum
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 33cb89cb-c967-760c-6bc4-94118a4f872c
ms.openlocfilehash: 59f43e8b3b0819b0178d60fa357e01937ae19d81
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322097"
---
# <a name="iolkenum"></a><span data-ttu-id="c06e7-102">IOlkEnum</span><span class="sxs-lookup"><span data-stu-id="c06e7-102">IOlkEnum</span></span>

<span data-ttu-id="c06e7-103">支持将帐户枚举为[IUnknown](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown)对象。</span><span class="sxs-lookup"><span data-stu-id="c06e7-103">Supports enumerating accounts as [IUnknown](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown) objects.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="c06e7-104">快速信息</span><span class="sxs-lookup"><span data-stu-id="c06e7-104">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c06e7-105">继承自:</span><span class="sxs-lookup"><span data-stu-id="c06e7-105">Inherits from:</span></span>  <br/> |[<span data-ttu-id="c06e7-106">IUnknown</span><span class="sxs-lookup"><span data-stu-id="c06e7-106">IUnknown</span></span>](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown) <br/> |
|<span data-ttu-id="c06e7-107">实现者：</span><span class="sxs-lookup"><span data-stu-id="c06e7-107">Implemented by:</span></span>  <br/> |<span data-ttu-id="c06e7-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="c06e7-108">Outlook</span></span>  <br/> |
|<span data-ttu-id="c06e7-109">提供者：</span><span class="sxs-lookup"><span data-stu-id="c06e7-109">Provided by:</span></span>  <br/> |[<span data-ttu-id="c06e7-110">IOlkAccountManager::EnumerateAccounts</span><span class="sxs-lookup"><span data-stu-id="c06e7-110">IOlkAccountManager::EnumerateAccounts</span></span>](iolkaccountmanager-enumerateaccounts.md) <br/> |
|<span data-ttu-id="c06e7-111">调用者：</span><span class="sxs-lookup"><span data-stu-id="c06e7-111">Called by:</span></span>  <br/> |<span data-ttu-id="c06e7-112">客户端</span><span class="sxs-lookup"><span data-stu-id="c06e7-112">Client</span></span>  <br/> |
|<span data-ttu-id="c06e7-113">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="c06e7-113">Interface identifier:</span></span>  <br/> |<span data-ttu-id="c06e7-114">IID_IOlkEnum</span><span class="sxs-lookup"><span data-stu-id="c06e7-114">IID_IOlkEnum</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="c06e7-115">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="c06e7-115">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="c06e7-116">GetCount</span><span class="sxs-lookup"><span data-stu-id="c06e7-116">GetCount</span></span>](iolkenum-getcount.md) <br/> |<span data-ttu-id="c06e7-117">获取枚举数中的帐户数。</span><span class="sxs-lookup"><span data-stu-id="c06e7-117">Gets the number of accounts in the enumerator.</span></span>  <br/> |
|[<span data-ttu-id="c06e7-118">Reset</span><span class="sxs-lookup"><span data-stu-id="c06e7-118">Reset</span></span>](iolkenum-reset.md) <br/> |<span data-ttu-id="c06e7-119">将枚举器重置到开头。</span><span class="sxs-lookup"><span data-stu-id="c06e7-119">Resets the enumerator to the beginning.</span></span>  <br/> |
|[<span data-ttu-id="c06e7-120">GetNext</span><span class="sxs-lookup"><span data-stu-id="c06e7-120">GetNext</span></span>](iolkenum-getnext.md) <br/> |<span data-ttu-id="c06e7-121">获取枚举数中的下一个帐户。</span><span class="sxs-lookup"><span data-stu-id="c06e7-121">Gets the next account in the enumerator.</span></span>  <br/> |
|[<span data-ttu-id="c06e7-122">Skip</span><span class="sxs-lookup"><span data-stu-id="c06e7-122">Skip</span></span>](iolkenum-skip.md) <br/> |<span data-ttu-id="c06e7-123">在枚举数中跳过指定数量的帐户。</span><span class="sxs-lookup"><span data-stu-id="c06e7-123">Skips a specified number of accounts in the enumerator.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c06e7-124">注解</span><span class="sxs-lookup"><span data-stu-id="c06e7-124">Remarks</span></span>

<span data-ttu-id="c06e7-125">在获取帐户枚举器时, **IOlkAccountManager:: EnumerateAccounts**返回此接口。</span><span class="sxs-lookup"><span data-stu-id="c06e7-125">This interface is returned by **IOlkAccountManager::EnumerateAccounts** when obtaining an enumerator of accounts.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c06e7-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c06e7-126">See also</span></span>

- [<span data-ttu-id="c06e7-127">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="c06e7-127">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="c06e7-128">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="c06e7-128">Constants (Account management API)</span></span>](constants-account-management-api.md)

