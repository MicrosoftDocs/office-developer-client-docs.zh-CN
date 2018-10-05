---
title: IOlkAccountHelperGetMapiSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a431787c-6e9a-9be1-165f-98c778d12e3e
description: 打开 MAPI 会话，并为帐户管理器中维护会话的引用。
ms.openlocfilehash: 5886ac1ae1bb8f3b43e09f49e48434d9a73656ce
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392598"
---
# <a name="iolkaccounthelpergetmapisession"></a><span data-ttu-id="8cf39-103">IOlkAccountHelper::GetMapiSession</span><span class="sxs-lookup"><span data-stu-id="8cf39-103">IOlkAccountHelper::GetMapiSession</span></span>

<span data-ttu-id="8cf39-104">打开 MAPI 会话，并为帐户管理器中维护会话的引用。</span><span class="sxs-lookup"><span data-stu-id="8cf39-104">Opens a MAPI session and maintains a reference to the session for the account manager.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="8cf39-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="8cf39-105">Quick info</span></span>

<span data-ttu-id="8cf39-106">请参阅[IOlkAccountHelper](iolkaccounthelper.md)。</span><span class="sxs-lookup"><span data-stu-id="8cf39-106">See [IOlkAccountHelper](iolkaccounthelper.md).</span></span>
  
```cpp
HRESULT IOlkAccountHelper::GetMapiSession(  
    LPUNKNOWN *ppmsess 
);
```

## <a name="parameters"></a><span data-ttu-id="8cf39-107">参数</span><span class="sxs-lookup"><span data-stu-id="8cf39-107">Parameters</span></span>

<span data-ttu-id="8cf39-108">_ppmsess_</span><span class="sxs-lookup"><span data-stu-id="8cf39-108">_ppmsess_</span></span>
  
> <span data-ttu-id="8cf39-109">[输出]当前的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="8cf39-109">[out] The current MAPI session.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="8cf39-110">返回值</span><span class="sxs-lookup"><span data-stu-id="8cf39-110">Return values</span></span>

<span data-ttu-id="8cf39-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="8cf39-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8cf39-112">注释</span><span class="sxs-lookup"><span data-stu-id="8cf39-112">Remarks</span></span>

<span data-ttu-id="8cf39-113">由于循环引用问题的帐户管理器本身不能 MAPI 会话维护引用。</span><span class="sxs-lookup"><span data-stu-id="8cf39-113">Because of circular reference problems, the account manager itself cannot maintain the reference for the MAPI session.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8cf39-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cf39-114">See also</span></span>

- [<span data-ttu-id="8cf39-115">IOlkAccountHelper::HandsOffSession</span><span class="sxs-lookup"><span data-stu-id="8cf39-115">IOlkAccountHelper::HandsOffSession</span></span>](iolkaccounthelper-handsoffsession.md)
- [<span data-ttu-id="8cf39-116">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8cf39-116">IMAPISession : IUnknown</span></span>](https://msdn.microsoft.com/library/5650fa2a-6e62-451c-964e-363f7bee2344%28Office.15%29.aspx)

