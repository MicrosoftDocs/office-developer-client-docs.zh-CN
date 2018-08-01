---
title: IOlkAccountHelperHandsOffSession
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9f71fdef-5df5-0892-b64c-293a2f22f5c3
description: 释放 IOlkAccountHelper::GetMapiSession 返回的 MAPI 会话对象。
ms.openlocfilehash: 71931be73e75e858224d3da2c92071341ac45e72
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774327"
---
# <a name="iolkaccounthelperhandsoffsession"></a><span data-ttu-id="07d8d-103">IOlkAccountHelper::HandsOffSession</span><span class="sxs-lookup"><span data-stu-id="07d8d-103">IOlkAccountHelper::HandsOffSession</span></span>

<span data-ttu-id="07d8d-104">释放由- [IOlkAccountHelper::GetMapiSession](iolkaccounthelper-getmapisession.md)返回的 MAPI 会话对象。</span><span class="sxs-lookup"><span data-stu-id="07d8d-104">Releases the MAPI session object that was returned by - [IOlkAccountHelper::GetMapiSession](iolkaccounthelper-getmapisession.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="07d8d-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="07d8d-105">Quick info</span></span>

<span data-ttu-id="07d8d-106">请参阅[IOlkAccountHelper](iolkaccounthelper.md)。</span><span class="sxs-lookup"><span data-stu-id="07d8d-106">See [IOlkAccountHelper](iolkaccounthelper.md).</span></span>
  
```cpp
HRESULT IOlkAccountHelper::HandsOffSession( );
```

## <a name="return-values"></a><span data-ttu-id="07d8d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="07d8d-107">Return values</span></span>

|<span data-ttu-id="07d8d-108">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="07d8d-108">**HRESULT**</span></span>|<span data-ttu-id="07d8d-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="07d8d-109">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07d8d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="07d8d-110">S_OK</span></span>  <br/> |<span data-ttu-id="07d8d-111">如果您的实现的**IOlkAccountHelper**创建**IOlkAccountHelper::GetMapiSession**返回自己 MAPI 会话，必须释放此处会话并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="07d8d-111">If your implementation of **IOlkAccountHelper** creates its own MAPI session that is returned in **IOlkAccountHelper::GetMapiSession**, you must release the session here and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="07d8d-112">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="07d8d-112">E_NOTIMPL</span></span>  <br/> |<span data-ttu-id="07d8d-113">如果您的实现的**IOlkAccountHelper**没有创建自己的 MAPI 会话，您必须返回仅 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="07d8d-113">If your implementation of **IOlkAccountHelper** did not create its own MAPI session, you must return only E_NOTIMPL.</span></span> <span data-ttu-id="07d8d-114">在这种情况下，这是唯一受支持的返回值。</span><span class="sxs-lookup"><span data-stu-id="07d8d-114">In this case, this is the only supported return value.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="07d8d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07d8d-115">See also</span></span>

- [<span data-ttu-id="07d8d-116">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="07d8d-116">Constants (Account management API)</span></span>](constants-account-management-api.md)  
- [<span data-ttu-id="07d8d-117">IOlkAccountHelper::GetMapiSession</span><span class="sxs-lookup"><span data-stu-id="07d8d-117">IOlkAccountHelper::GetMapiSession</span></span>](iolkaccounthelper-getmapisession.md)

