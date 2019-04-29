---
title: PingSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4646659b-f932-4d11-a46f-4231bb397243
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 0fa5fe57e537a7b8c7d880b934809a6f68ce27a2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408360"
---
# <a name="pingsession"></a><span data-ttu-id="1c84f-103">PingSession</span><span class="sxs-lookup"><span data-stu-id="1c84f-103">PingSession</span></span>

<span data-ttu-id="1c84f-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1c84f-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="1c84f-105">检查会话是否有效。</span><span class="sxs-lookup"><span data-stu-id="1c84f-105">Checks whether a session is valid.</span></span> <span data-ttu-id="1c84f-106">当 Excel 需要确定以前返回的会话 ID 是否仍处于活动状态且可以使用时, 通常会调用此函数。</span><span class="sxs-lookup"><span data-stu-id="1c84f-106">This function is typically called when Excel needs to determine if a previously returned session ID is still active and can be used.</span></span>
  
```cpp
int PingSession(int SessionId)
```

## <a name="parameters"></a><span data-ttu-id="1c84f-107">参数</span><span class="sxs-lookup"><span data-stu-id="1c84f-107">Parameters</span></span>

<span data-ttu-id="1c84f-108">_SessionID_</span><span class="sxs-lookup"><span data-stu-id="1c84f-108">_SessionID_</span></span>
  
> <span data-ttu-id="1c84f-109">要 ping 的会话的 ID。</span><span class="sxs-lookup"><span data-stu-id="1c84f-109">The ID of the session to ping.</span></span> <span data-ttu-id="1c84f-110">此值必须与上一次调用[OpenSession](opensession.md)所返回的 ID 相匹配。</span><span class="sxs-lookup"><span data-stu-id="1c84f-110">This value must match an ID returned by a previous call to [OpenSession](opensession.md).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1c84f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="1c84f-111">Return value</span></span>

<span data-ttu-id="1c84f-112">如果_SessionId_参数有效, 则为**xlHpcRetSuccess** , 否则为 false。否则**xlHpcRetInvalidSessionId**。</span><span class="sxs-lookup"><span data-stu-id="1c84f-112">**xlHpcRetSuccess** if the  _SessionId_ argument is valid; otherwise **xlHpcRetInvalidSessionId**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c84f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c84f-113">See also</span></span>

- [<span data-ttu-id="1c84f-114">OpenSession</span><span class="sxs-lookup"><span data-stu-id="1c84f-114">OpenSession</span></span>](opensession.md)
- [<span data-ttu-id="1c84f-115">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="1c84f-115">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

