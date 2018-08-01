---
title: IOlkAccountHelper
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fc2972da-80e9-50e2-10b3-585eb63e9103
ms.openlocfilehash: 3c28b1e8ab7e2d72d27cc6545b6ef57834ef5b6f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774326"
---
# <a name="iolkaccounthelper"></a><span data-ttu-id="09dcd-102">IOlkAccountHelper</span><span class="sxs-lookup"><span data-stu-id="09dcd-102">IOlkAccountHelper</span></span>

<span data-ttu-id="09dcd-103">在当前的 MAPI 会话管理帐户中提供的帮助器功能。</span><span class="sxs-lookup"><span data-stu-id="09dcd-103">Provides helper functionality in the current MAPI session to manage accounts.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="09dcd-104">快速信息</span><span class="sxs-lookup"><span data-stu-id="09dcd-104">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="09dcd-105">继承：</span><span class="sxs-lookup"><span data-stu-id="09dcd-105">Inherits from:</span></span>  <br/> |[<span data-ttu-id="09dcd-106">IUnknown</span><span class="sxs-lookup"><span data-stu-id="09dcd-106">IUnknown</span></span>](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) <br/> |
|<span data-ttu-id="09dcd-107">提供者：</span><span class="sxs-lookup"><span data-stu-id="09dcd-107">Provided by:</span></span>  <br/> |<span data-ttu-id="09dcd-108">客户端</span><span class="sxs-lookup"><span data-stu-id="09dcd-108">Client</span></span>  <br/> |
|<span data-ttu-id="09dcd-109">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="09dcd-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="09dcd-110">IID_IOlkAccountHelper</span><span class="sxs-lookup"><span data-stu-id="09dcd-110">IID_IOlkAccountHelper</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="09dcd-111">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="09dcd-111">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="09dcd-112">Placeholder1</span><span class="sxs-lookup"><span data-stu-id="09dcd-112">Placeholder1</span></span>](iolkaccounthelper-placeholder1.md) <br/> | <span data-ttu-id="09dcd-113">*此成员是一个占位符，不支持。*</span><span class="sxs-lookup"><span data-stu-id="09dcd-113">*This member is a placeholder and is not supported.*</span></span>  <br/> |
|[<span data-ttu-id="09dcd-114">GetIdentity</span><span class="sxs-lookup"><span data-stu-id="09dcd-114">GetIdentity</span></span>](iolkaccounthelper-getidentity.md) <br/> |<span data-ttu-id="09dcd-115">获取帐户的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="09dcd-115">Gets the profile name of an account.</span></span>  <br/> |
|[<span data-ttu-id="09dcd-116">GetMapiSession</span><span class="sxs-lookup"><span data-stu-id="09dcd-116">GetMapiSession</span></span>](iolkaccounthelper-getmapisession.md) <br/> |<span data-ttu-id="09dcd-117">打开 MAPI 会话，并为帐户管理器中维护会话的引用。</span><span class="sxs-lookup"><span data-stu-id="09dcd-117">Opens a MAPI session and maintains a reference to the session for the account manager.</span></span>  <br/> |
|[<span data-ttu-id="09dcd-118">HandsOffSession</span><span class="sxs-lookup"><span data-stu-id="09dcd-118">HandsOffSession</span></span>](iolkaccounthelper-handsoffsession.md) <br/> |<span data-ttu-id="09dcd-119">释放[IOlkAccountHelper::GetMapiSession](iolkaccounthelper-getmapisession.md)返回的 MAPI 会话对象。</span><span class="sxs-lookup"><span data-stu-id="09dcd-119">Releases the MAPI session object that was returned by [IOlkAccountHelper::GetMapiSession](iolkaccounthelper-getmapisession.md).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="09dcd-120">说明</span><span class="sxs-lookup"><span data-stu-id="09dcd-120">Remarks</span></span>

<span data-ttu-id="09dcd-121">初始化帐户管理器时，该接口被传递给[IOlkAccountManager::Init](iolkaccountmanager-init.md) 。</span><span class="sxs-lookup"><span data-stu-id="09dcd-121">This interface is passed to [IOlkAccountManager::Init](iolkaccountmanager-init.md) when initializing the account manager.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="09dcd-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09dcd-122">See also</span></span>

- [<span data-ttu-id="09dcd-123">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="09dcd-123">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="09dcd-124">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="09dcd-124">Constants (Account management API)</span></span>](constants-account-management-api.md)

