---
title: IOlkAccountHelperGetMapiSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a431787c-6e9a-9be1-165f-98c778d12e3e
description: 打开 MAPI 会话并维护对帐户管理员会话的引用。
ms.openlocfilehash: 5886ac1ae1bb8f3b43e09f49e48434d9a73656ce
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322174"
---
# <a name="iolkaccounthelpergetmapisession"></a><span data-ttu-id="49cc1-103">IOlkAccountHelper::GetMapiSession</span><span class="sxs-lookup"><span data-stu-id="49cc1-103">IOlkAccountHelper::GetMapiSession</span></span>

<span data-ttu-id="49cc1-104">打开 MAPI 会话并维护对帐户管理员会话的引用。</span><span class="sxs-lookup"><span data-stu-id="49cc1-104">Opens a MAPI session and maintains a reference to the session for the account manager.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="49cc1-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="49cc1-105">Quick info</span></span>

<span data-ttu-id="49cc1-106">请参阅[IOlkAccountHelper](iolkaccounthelper.md)。</span><span class="sxs-lookup"><span data-stu-id="49cc1-106">See [IOlkAccountHelper](iolkaccounthelper.md).</span></span>
  
```cpp
HRESULT IOlkAccountHelper::GetMapiSession(  
    LPUNKNOWN *ppmsess 
);
```

## <a name="parameters"></a><span data-ttu-id="49cc1-107">参数</span><span class="sxs-lookup"><span data-stu-id="49cc1-107">Parameters</span></span>

<span data-ttu-id="49cc1-108">_ppmsess_</span><span class="sxs-lookup"><span data-stu-id="49cc1-108">_ppmsess_</span></span>
  
> <span data-ttu-id="49cc1-109">排除当前的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="49cc1-109">[out] The current MAPI session.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="49cc1-110">返回值</span><span class="sxs-lookup"><span data-stu-id="49cc1-110">Return values</span></span>

<span data-ttu-id="49cc1-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="49cc1-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="49cc1-112">注解</span><span class="sxs-lookup"><span data-stu-id="49cc1-112">Remarks</span></span>

<span data-ttu-id="49cc1-113">由于存在循环引用问题, 帐户管理员本身无法维护对 MAPI 会话的引用。</span><span class="sxs-lookup"><span data-stu-id="49cc1-113">Because of circular reference problems, the account manager itself cannot maintain the reference for the MAPI session.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="49cc1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49cc1-114">See also</span></span>

- [<span data-ttu-id="49cc1-115">IOlkAccountHelper::HandsOffSession</span><span class="sxs-lookup"><span data-stu-id="49cc1-115">IOlkAccountHelper::HandsOffSession</span></span>](iolkaccounthelper-handsoffsession.md)
- [<span data-ttu-id="49cc1-116">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="49cc1-116">IMAPISession : IUnknown</span></span>](https://msdn.microsoft.com/library/5650fa2a-6e62-451c-964e-363f7bee2344%28Office.15%29.aspx)

