---
title: IOlkAccountNotify
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 360854bb-e9be-a784-e80b-3f18418ded1b
ms.openlocfilehash: f4b57ad1062df9aa1809e8eb422a2c983adcac4a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774357"
---
# <a name="iolkaccountnotify"></a><span data-ttu-id="4fb32-102">IOlkAccountNotify</span><span class="sxs-lookup"><span data-stu-id="4fb32-102">IOlkAccountNotify</span></span>

<span data-ttu-id="4fb32-103">为帐户的更改到客户端提供回调。</span><span class="sxs-lookup"><span data-stu-id="4fb32-103">Provides a callback to the client for changes to an account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="4fb32-104">快速信息</span><span class="sxs-lookup"><span data-stu-id="4fb32-104">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4fb32-105">继承：</span><span class="sxs-lookup"><span data-stu-id="4fb32-105">Inherits from:</span></span>  <br/> |[<span data-ttu-id="4fb32-106">IOlkErrorUnknown</span><span class="sxs-lookup"><span data-stu-id="4fb32-106">IOlkErrorUnknown</span></span>](iolkerrorunknown.md) <br/> |
|<span data-ttu-id="4fb32-107">提供者：</span><span class="sxs-lookup"><span data-stu-id="4fb32-107">Provided by:</span></span>  <br/> | <span data-ttu-id="4fb32-108">客户端</span><span class="sxs-lookup"><span data-stu-id="4fb32-108">Client</span></span>  <br/> |
|<span data-ttu-id="4fb32-109">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="4fb32-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="4fb32-110">IID_IOlkAccountNotify</span><span class="sxs-lookup"><span data-stu-id="4fb32-110">IID_IOlkAccountNotify</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="4fb32-111">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="4fb32-111">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="4fb32-112">Notify</span><span class="sxs-lookup"><span data-stu-id="4fb32-112">Notify</span></span>](iolkaccountnotify-notify.md) <br/> |<span data-ttu-id="4fb32-113">通知客户端到指定的帐户的更改。</span><span class="sxs-lookup"><span data-stu-id="4fb32-113">Notifies the client of changes to the specified account.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4fb32-114">说明</span><span class="sxs-lookup"><span data-stu-id="4fb32-114">Remarks</span></span>

<span data-ttu-id="4fb32-115">设置通知时，该接口被传递给[IOlkAccountManager::Advise](iolkaccountmanager-advise.md) 。</span><span class="sxs-lookup"><span data-stu-id="4fb32-115">This interface is passed to [IOlkAccountManager::Advise](iolkaccountmanager-advise.md) when setting up notifications.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4fb32-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fb32-116">See also</span></span>

- [<span data-ttu-id="4fb32-117">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="4fb32-117">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="4fb32-118">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="4fb32-118">Constants (Account management API)</span></span>](constants-account-management-api.md)

