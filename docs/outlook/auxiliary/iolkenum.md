---
title: IOlkEnum
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 33cb89cb-c967-760c-6bc4-94118a4f872c
ms.openlocfilehash: 19ec67bf033859073e7685912196369b664f4a36
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592687"
---
# <a name="iolkenum"></a><span data-ttu-id="06769-102">IOlkEnum</span><span class="sxs-lookup"><span data-stu-id="06769-102">IOlkEnum</span></span>

<span data-ttu-id="06769-103">支持枚举作为[IUnknown](https://docs.microsoft.com/en-us/windows/desktop/api/unknwn/nn-unknwn-iunknown)对象的帐户。</span><span class="sxs-lookup"><span data-stu-id="06769-103">Supports enumerating accounts as [IUnknown](https://docs.microsoft.com/en-us/windows/desktop/api/unknwn/nn-unknwn-iunknown) objects.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="06769-104">快速信息</span><span class="sxs-lookup"><span data-stu-id="06769-104">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="06769-105">继承：</span><span class="sxs-lookup"><span data-stu-id="06769-105">Inherits from:</span></span>  <br/> |[<span data-ttu-id="06769-106">IUnknown</span><span class="sxs-lookup"><span data-stu-id="06769-106">IUnknown</span></span>](https://docs.microsoft.com/en-us/windows/desktop/api/unknwn/nn-unknwn-iunknown) <br/> |
|<span data-ttu-id="06769-107">通过实现：</span><span class="sxs-lookup"><span data-stu-id="06769-107">Implemented by:</span></span>  <br/> |<span data-ttu-id="06769-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="06769-108">Outlook</span></span>  <br/> |
|<span data-ttu-id="06769-109">提供者：</span><span class="sxs-lookup"><span data-stu-id="06769-109">Provided by:</span></span>  <br/> |[<span data-ttu-id="06769-110">IOlkAccountManager::EnumerateAccounts</span><span class="sxs-lookup"><span data-stu-id="06769-110">IOlkAccountManager::EnumerateAccounts</span></span>](iolkaccountmanager-enumerateaccounts.md) <br/> |
|<span data-ttu-id="06769-111">调用：</span><span class="sxs-lookup"><span data-stu-id="06769-111">Called by:</span></span>  <br/> |<span data-ttu-id="06769-112">客户端</span><span class="sxs-lookup"><span data-stu-id="06769-112">Client</span></span>  <br/> |
|<span data-ttu-id="06769-113">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="06769-113">Interface identifier:</span></span>  <br/> |<span data-ttu-id="06769-114">IID_IOlkEnum</span><span class="sxs-lookup"><span data-stu-id="06769-114">IID_IOlkEnum</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="06769-115">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="06769-115">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="06769-116">GetCount</span><span class="sxs-lookup"><span data-stu-id="06769-116">GetCount</span></span>](iolkenum-getcount.md) <br/> |<span data-ttu-id="06769-117">获取枚举中的帐户数。</span><span class="sxs-lookup"><span data-stu-id="06769-117">Gets the number of accounts in the enumerator.</span></span>  <br/> |
|[<span data-ttu-id="06769-118">Reset</span><span class="sxs-lookup"><span data-stu-id="06769-118">Reset</span></span>](iolkenum-reset.md) <br/> |<span data-ttu-id="06769-119">重将枚举器重置到开头。</span><span class="sxs-lookup"><span data-stu-id="06769-119">Resets the enumerator to the beginning.</span></span>  <br/> |
|[<span data-ttu-id="06769-120">GetNext</span><span class="sxs-lookup"><span data-stu-id="06769-120">GetNext</span></span>](iolkenum-getnext.md) <br/> |<span data-ttu-id="06769-121">获取枚举中的下一个帐户。</span><span class="sxs-lookup"><span data-stu-id="06769-121">Gets the next account in the enumerator.</span></span>  <br/> |
|[<span data-ttu-id="06769-122">跳过</span><span class="sxs-lookup"><span data-stu-id="06769-122">Skip</span></span>](iolkenum-skip.md) <br/> |<span data-ttu-id="06769-123">跳过指定的数量的枚举中的帐户。</span><span class="sxs-lookup"><span data-stu-id="06769-123">Skips a specified number of accounts in the enumerator.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="06769-124">注解</span><span class="sxs-lookup"><span data-stu-id="06769-124">Remarks</span></span>

<span data-ttu-id="06769-125">此接口返回**IOlkAccountManager::EnumerateAccounts**时获取帐户的枚举。</span><span class="sxs-lookup"><span data-stu-id="06769-125">This interface is returned by **IOlkAccountManager::EnumerateAccounts** when obtaining an enumerator of accounts.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="06769-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06769-126">See also</span></span>

- [<span data-ttu-id="06769-127">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="06769-127">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="06769-128">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="06769-128">Constants (Account management API)</span></span>](constants-account-management-api.md)

