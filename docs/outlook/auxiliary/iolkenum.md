---
title: IOlkEnum
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 33cb89cb-c967-760c-6bc4-94118a4f872c
ms.openlocfilehash: be91a56f93b787f5570139768d96eb4f7fe9ac02
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774372"
---
# <a name="iolkenum"></a><span data-ttu-id="ed9c5-102">IOlkEnum</span><span class="sxs-lookup"><span data-stu-id="ed9c5-102">IOlkEnum</span></span>

<span data-ttu-id="ed9c5-103">支持枚举作为[IUnknown](http://msdn.microsoft.com/library/com.iunknown%28Office.15%29.aspx)对象的帐户。</span><span class="sxs-lookup"><span data-stu-id="ed9c5-103">Supports enumerating accounts as [IUnknown](http://msdn.microsoft.com/library/com.iunknown%28Office.15%29.aspx) objects.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="ed9c5-104">快速信息</span><span class="sxs-lookup"><span data-stu-id="ed9c5-104">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ed9c5-105">继承：</span><span class="sxs-lookup"><span data-stu-id="ed9c5-105">Inherits from:</span></span>  <br/> |[<span data-ttu-id="ed9c5-106">IUnknown</span><span class="sxs-lookup"><span data-stu-id="ed9c5-106">IUnknown</span></span>](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) <br/> |
|<span data-ttu-id="ed9c5-107">通过实现：</span><span class="sxs-lookup"><span data-stu-id="ed9c5-107">Implemented by:</span></span>  <br/> |<span data-ttu-id="ed9c5-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="ed9c5-108">Outlook</span></span>  <br/> |
|<span data-ttu-id="ed9c5-109">提供者：</span><span class="sxs-lookup"><span data-stu-id="ed9c5-109">Provided by:</span></span>  <br/> |[<span data-ttu-id="ed9c5-110">IOlkAccountManager::EnumerateAccounts</span><span class="sxs-lookup"><span data-stu-id="ed9c5-110">IOlkAccountManager::EnumerateAccounts</span></span>](iolkaccountmanager-enumerateaccounts.md) <br/> |
|<span data-ttu-id="ed9c5-111">调用：</span><span class="sxs-lookup"><span data-stu-id="ed9c5-111">Called by:</span></span>  <br/> |<span data-ttu-id="ed9c5-112">客户端</span><span class="sxs-lookup"><span data-stu-id="ed9c5-112">Client</span></span>  <br/> |
|<span data-ttu-id="ed9c5-113">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="ed9c5-113">Interface identifier:</span></span>  <br/> |<span data-ttu-id="ed9c5-114">IID_IOlkEnum</span><span class="sxs-lookup"><span data-stu-id="ed9c5-114">IID_IOlkEnum</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="ed9c5-115">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="ed9c5-115">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="ed9c5-116">GetCount</span><span class="sxs-lookup"><span data-stu-id="ed9c5-116">GetCount</span></span>](iolkenum-getcount.md) <br/> |<span data-ttu-id="ed9c5-117">获取枚举中的帐户数。</span><span class="sxs-lookup"><span data-stu-id="ed9c5-117">Gets the number of accounts in the enumerator.</span></span>  <br/> |
|[<span data-ttu-id="ed9c5-118">Reset</span><span class="sxs-lookup"><span data-stu-id="ed9c5-118">Reset</span></span>](iolkenum-reset.md) <br/> |<span data-ttu-id="ed9c5-119">重将枚举器重置到开头。</span><span class="sxs-lookup"><span data-stu-id="ed9c5-119">Resets the enumerator to the beginning.</span></span>  <br/> |
|[<span data-ttu-id="ed9c5-120">GetNext</span><span class="sxs-lookup"><span data-stu-id="ed9c5-120">GetNext</span></span>](iolkenum-getnext.md) <br/> |<span data-ttu-id="ed9c5-121">获取枚举中的下一个帐户。</span><span class="sxs-lookup"><span data-stu-id="ed9c5-121">Gets the next account in the enumerator.</span></span>  <br/> |
|[<span data-ttu-id="ed9c5-122">跳过</span><span class="sxs-lookup"><span data-stu-id="ed9c5-122">Skip</span></span>](iolkenum-skip.md) <br/> |<span data-ttu-id="ed9c5-123">跳过指定的数量的枚举中的帐户。</span><span class="sxs-lookup"><span data-stu-id="ed9c5-123">Skips a specified number of accounts in the enumerator.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ed9c5-124">说明</span><span class="sxs-lookup"><span data-stu-id="ed9c5-124">Remarks</span></span>

<span data-ttu-id="ed9c5-125">此接口返回**IOlkAccountManager::EnumerateAccounts**时获取帐户的枚举。</span><span class="sxs-lookup"><span data-stu-id="ed9c5-125">This interface is returned by **IOlkAccountManager::EnumerateAccounts** when obtaining an enumerator of accounts.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ed9c5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed9c5-126">See also</span></span>

- [<span data-ttu-id="ed9c5-127">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="ed9c5-127">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="ed9c5-128">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="ed9c5-128">Constants (Account management API)</span></span>](constants-account-management-api.md)

