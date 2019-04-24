---
title: IOlkAccountHelper
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fc2972da-80e9-50e2-10b3-585eb63e9103
ms.openlocfilehash: 241babe45b543fb00c0d2756a2e846303a1717b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322153"
---
# <a name="iolkaccounthelper"></a><span data-ttu-id="d0b3f-102">IOlkAccountHelper</span><span class="sxs-lookup"><span data-stu-id="d0b3f-102">IOlkAccountHelper</span></span>

<span data-ttu-id="d0b3f-103">提供当前 MAPI 会话中的帮助程序功能来管理帐户。</span><span class="sxs-lookup"><span data-stu-id="d0b3f-103">Provides helper functionality in the current MAPI session to manage accounts.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d0b3f-104">快速信息</span><span class="sxs-lookup"><span data-stu-id="d0b3f-104">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d0b3f-105">继承自:</span><span class="sxs-lookup"><span data-stu-id="d0b3f-105">Inherits from:</span></span>  <br/> |[<span data-ttu-id="d0b3f-106">IUnknown</span><span class="sxs-lookup"><span data-stu-id="d0b3f-106">IUnknown</span></span>](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) <br/> |
|<span data-ttu-id="d0b3f-107">提供者：</span><span class="sxs-lookup"><span data-stu-id="d0b3f-107">Provided by:</span></span>  <br/> |<span data-ttu-id="d0b3f-108">客户端</span><span class="sxs-lookup"><span data-stu-id="d0b3f-108">Client</span></span>  <br/> |
|<span data-ttu-id="d0b3f-109">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="d0b3f-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="d0b3f-110">IID_IOlkAccountHelper</span><span class="sxs-lookup"><span data-stu-id="d0b3f-110">IID_IOlkAccountHelper</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="d0b3f-111">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="d0b3f-111">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="d0b3f-112">Placeholder1</span><span class="sxs-lookup"><span data-stu-id="d0b3f-112">Placeholder1</span></span>](iolkaccounthelper-placeholder1.md) <br/> | <span data-ttu-id="d0b3f-113">*此成员是占位符, 不受支持。*</span><span class="sxs-lookup"><span data-stu-id="d0b3f-113">*This member is a placeholder and is not supported.*</span></span>  <br/> |
|[<span data-ttu-id="d0b3f-114">GetIdentity</span><span class="sxs-lookup"><span data-stu-id="d0b3f-114">GetIdentity</span></span>](iolkaccounthelper-getidentity.md) <br/> |<span data-ttu-id="d0b3f-115">获取帐户的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="d0b3f-115">Gets the profile name of an account.</span></span>  <br/> |
|[<span data-ttu-id="d0b3f-116">GetMapiSession</span><span class="sxs-lookup"><span data-stu-id="d0b3f-116">GetMapiSession</span></span>](iolkaccounthelper-getmapisession.md) <br/> |<span data-ttu-id="d0b3f-117">打开 MAPI 会话并维护对帐户管理员会话的引用。</span><span class="sxs-lookup"><span data-stu-id="d0b3f-117">Opens a MAPI session and maintains a reference to the session for the account manager.</span></span>  <br/> |
|[<span data-ttu-id="d0b3f-118">HandsOffSession</span><span class="sxs-lookup"><span data-stu-id="d0b3f-118">HandsOffSession</span></span>](iolkaccounthelper-handsoffsession.md) <br/> |<span data-ttu-id="d0b3f-119">释放[IOlkAccountHelper:: GetMapiSession](iolkaccounthelper-getmapisession.md)返回的 MAPI session 对象。</span><span class="sxs-lookup"><span data-stu-id="d0b3f-119">Releases the MAPI session object that was returned by [IOlkAccountHelper::GetMapiSession](iolkaccounthelper-getmapisession.md).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d0b3f-120">注解</span><span class="sxs-lookup"><span data-stu-id="d0b3f-120">Remarks</span></span>

<span data-ttu-id="d0b3f-121">初始化帐户管理器时, 此接口将传递给[IOlkAccountManager:: Init](iolkaccountmanager-init.md) 。</span><span class="sxs-lookup"><span data-stu-id="d0b3f-121">This interface is passed to [IOlkAccountManager::Init](iolkaccountmanager-init.md) when initializing the account manager.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d0b3f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0b3f-122">See also</span></span>

- [<span data-ttu-id="d0b3f-123">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="d0b3f-123">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="d0b3f-124">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="d0b3f-124">Constants (Account management API)</span></span>](constants-account-management-api.md)

