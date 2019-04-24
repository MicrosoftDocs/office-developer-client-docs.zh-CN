---
title: IOlkAccountNotify
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 360854bb-e9be-a784-e80b-3f18418ded1b
ms.openlocfilehash: ab24feca84e7049a9800b860c332db52d19cf929
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322069"
---
# <a name="iolkaccountnotify"></a><span data-ttu-id="2de9d-102">IOlkAccountNotify</span><span class="sxs-lookup"><span data-stu-id="2de9d-102">IOlkAccountNotify</span></span>

<span data-ttu-id="2de9d-103">为客户端提供对帐户更改的回调。</span><span class="sxs-lookup"><span data-stu-id="2de9d-103">Provides a callback to the client for changes to an account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="2de9d-104">快速信息</span><span class="sxs-lookup"><span data-stu-id="2de9d-104">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2de9d-105">继承自:</span><span class="sxs-lookup"><span data-stu-id="2de9d-105">Inherits from:</span></span>  <br/> |[<span data-ttu-id="2de9d-106">IOlkErrorUnknown</span><span class="sxs-lookup"><span data-stu-id="2de9d-106">IOlkErrorUnknown</span></span>](iolkerrorunknown.md) <br/> |
|<span data-ttu-id="2de9d-107">提供者：</span><span class="sxs-lookup"><span data-stu-id="2de9d-107">Provided by:</span></span>  <br/> | <span data-ttu-id="2de9d-108">客户端</span><span class="sxs-lookup"><span data-stu-id="2de9d-108">Client</span></span>  <br/> |
|<span data-ttu-id="2de9d-109">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="2de9d-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="2de9d-110">IID_IOlkAccountNotify</span><span class="sxs-lookup"><span data-stu-id="2de9d-110">IID_IOlkAccountNotify</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="2de9d-111">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="2de9d-111">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="2de9d-112">Notify</span><span class="sxs-lookup"><span data-stu-id="2de9d-112">Notify</span></span>](iolkaccountnotify-notify.md) <br/> |<span data-ttu-id="2de9d-113">通知客户端对指定帐户所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2de9d-113">Notifies the client of changes to the specified account.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2de9d-114">注解</span><span class="sxs-lookup"><span data-stu-id="2de9d-114">Remarks</span></span>

<span data-ttu-id="2de9d-115">在设置通知时, 此接口将传递给[IOlkAccountManager:: Advise](iolkaccountmanager-advise.md) 。</span><span class="sxs-lookup"><span data-stu-id="2de9d-115">This interface is passed to [IOlkAccountManager::Advise](iolkaccountmanager-advise.md) when setting up notifications.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2de9d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2de9d-116">See also</span></span>

- [<span data-ttu-id="2de9d-117">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="2de9d-117">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="2de9d-118">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="2de9d-118">Constants (Account management API)</span></span>](constants-account-management-api.md)

