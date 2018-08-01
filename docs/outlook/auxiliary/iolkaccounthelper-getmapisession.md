---
title: IOlkAccountHelperGetMapiSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a431787c-6e9a-9be1-165f-98c778d12e3e
description: 打开 MAPI 会话，并为帐户管理器中维护会话的引用。
ms.openlocfilehash: 50809a00d13fd9f2a93bebc2961a134b3625e82c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774352"
---
# <a name="iolkaccounthelpergetmapisession"></a><span data-ttu-id="5d144-103">IOlkAccountHelper::GetMapiSession</span><span class="sxs-lookup"><span data-stu-id="5d144-103">IOlkAccountHelper::GetMapiSession</span></span>

<span data-ttu-id="5d144-104">打开 MAPI 会话，并为帐户管理器中维护会话的引用。</span><span class="sxs-lookup"><span data-stu-id="5d144-104">Opens a MAPI session and maintains a reference to the session for the account manager.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5d144-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="5d144-105">Quick info</span></span>

<span data-ttu-id="5d144-106">请参阅[IOlkAccountHelper](iolkaccounthelper.md)。</span><span class="sxs-lookup"><span data-stu-id="5d144-106">See [IOlkAccountHelper](iolkaccounthelper.md).</span></span>
  
```cpp
HRESULT IOlkAccountHelper::GetMapiSession(  
    LPUNKNOWN *ppmsess 
);
```

## <a name="parameters"></a><span data-ttu-id="5d144-107">参数</span><span class="sxs-lookup"><span data-stu-id="5d144-107">Parameters</span></span>

<span data-ttu-id="5d144-108">_ppmsess_</span><span class="sxs-lookup"><span data-stu-id="5d144-108">_ppmsess_</span></span>
  
> <span data-ttu-id="5d144-109">[输出]当前的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="5d144-109">[out] The current MAPI session.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="5d144-110">返回值</span><span class="sxs-lookup"><span data-stu-id="5d144-110">Return values</span></span>

<span data-ttu-id="5d144-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="5d144-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5d144-112">注释</span><span class="sxs-lookup"><span data-stu-id="5d144-112">Remarks</span></span>

<span data-ttu-id="5d144-113">由于循环引用问题的帐户管理器本身不能 MAPI 会话维护引用。</span><span class="sxs-lookup"><span data-stu-id="5d144-113">Because of circular reference problems, the account manager itself cannot maintain the reference for the MAPI session.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d144-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d144-114">See also</span></span>

- [<span data-ttu-id="5d144-115">IOlkAccountHelper::HandsOffSession</span><span class="sxs-lookup"><span data-stu-id="5d144-115">IOlkAccountHelper::HandsOffSession</span></span>](iolkaccounthelper-handsoffsession.md)
- [<span data-ttu-id="5d144-116">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5d144-116">IMAPISession : IUnknown</span></span>](http://msdn.microsoft.com/library/5650fa2a-6e62-451c-964e-363f7bee2344%28Office.15%29.aspx)

