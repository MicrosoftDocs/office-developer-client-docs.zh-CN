---
title: IOlkAccountHelperHandsOffSession
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9f71fdef-5df5-0892-b64c-293a2f22f5c3
description: '释放 IOlkAccountHelper:: GetMapiSession 返回的 MAPI session 对象。'
ms.openlocfilehash: c481cee1ecb8c2bd3997cdee8ae86c9c3b5a712e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322090"
---
# <a name="iolkaccounthelperhandsoffsession"></a><span data-ttu-id="bb2c1-103">IOlkAccountHelper::HandsOffSession</span><span class="sxs-lookup"><span data-stu-id="bb2c1-103">IOlkAccountHelper::HandsOffSession</span></span>

<span data-ttu-id="bb2c1-104">释放由- [IOlkAccountHelper:: GetMapiSession](iolkaccounthelper-getmapisession.md)返回的 MAPI 会话对象。</span><span class="sxs-lookup"><span data-stu-id="bb2c1-104">Releases the MAPI session object that was returned by - [IOlkAccountHelper::GetMapiSession](iolkaccounthelper-getmapisession.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="bb2c1-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="bb2c1-105">Quick info</span></span>

<span data-ttu-id="bb2c1-106">请参阅[IOlkAccountHelper](iolkaccounthelper.md)。</span><span class="sxs-lookup"><span data-stu-id="bb2c1-106">See [IOlkAccountHelper](iolkaccounthelper.md).</span></span>
  
```cpp
HRESULT IOlkAccountHelper::HandsOffSession( );
```

## <a name="return-values"></a><span data-ttu-id="bb2c1-107">返回值</span><span class="sxs-lookup"><span data-stu-id="bb2c1-107">Return values</span></span>

|<span data-ttu-id="bb2c1-108">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="bb2c1-108">**HRESULT**</span></span>|<span data-ttu-id="bb2c1-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="bb2c1-109">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bb2c1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb2c1-110">S_OK</span></span>  <br/> |<span data-ttu-id="bb2c1-111">如果您的**IOlkAccountHelper**实现创建其自己的在**IOlkAccountHelper:: GetMapiSession**中返回的 MAPI 会话, 则必须在此处发布会话并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="bb2c1-111">If your implementation of **IOlkAccountHelper** creates its own MAPI session that is returned in **IOlkAccountHelper::GetMapiSession**, you must release the session here and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="bb2c1-112">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="bb2c1-112">E_NOTIMPL</span></span>  <br/> |<span data-ttu-id="bb2c1-113">如果您的**IOlkAccountHelper**实现没有创建自己的 MAPI 会话, 则必须仅返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="bb2c1-113">If your implementation of **IOlkAccountHelper** did not create its own MAPI session, you must return only E_NOTIMPL.</span></span> <span data-ttu-id="bb2c1-114">在这种情况下, 这是唯一受支持的返回值。</span><span class="sxs-lookup"><span data-stu-id="bb2c1-114">In this case, this is the only supported return value.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bb2c1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb2c1-115">See also</span></span>

- [<span data-ttu-id="bb2c1-116">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="bb2c1-116">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="bb2c1-117">IOlkAccountHelper::GetMapiSession</span><span class="sxs-lookup"><span data-stu-id="bb2c1-117">IOlkAccountHelper::GetMapiSession</span></span>](iolkaccounthelper-getmapisession.md)

