---
title: PingSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4646659b-f932-4d11-a46f-4231bb397243
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 165be9eada54b2030471fc10e7a0bf0c7dcc7c8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773820"
---
# <a name="pingsession"></a><span data-ttu-id="38c18-103">PingSession</span><span class="sxs-lookup"><span data-stu-id="38c18-103">PingSession</span></span>

<span data-ttu-id="38c18-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="38c18-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="38c18-105">检查会话是否有效。</span><span class="sxs-lookup"><span data-stu-id="38c18-105">Checks whether a session is valid.</span></span> <span data-ttu-id="38c18-106">当需要确定是否以前返回的会话 ID 仍处于活动状态，可以使用 Excel 通常调用此函数。</span><span class="sxs-lookup"><span data-stu-id="38c18-106">This function is typically called when Excel needs to determine if a previously returned session ID is still active and can be used.</span></span>
  
```cpp
int PingSession(int SessionId)
```

## <a name="parameters"></a><span data-ttu-id="38c18-107">参数</span><span class="sxs-lookup"><span data-stu-id="38c18-107">Parameters</span></span>

<span data-ttu-id="38c18-108">_SessionID_</span><span class="sxs-lookup"><span data-stu-id="38c18-108">_SessionID_</span></span>
  
> <span data-ttu-id="38c18-109">Ping 会话的 ID。</span><span class="sxs-lookup"><span data-stu-id="38c18-109">The ID of the session to ping.</span></span> <span data-ttu-id="38c18-110">此值必须匹配由[OpenSession](opensession.md)以前调用返回的 ID。</span><span class="sxs-lookup"><span data-stu-id="38c18-110">This value must match an ID returned by a previous call to [OpenSession](opensession.md).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="38c18-111">返回值</span><span class="sxs-lookup"><span data-stu-id="38c18-111">Return value</span></span>

<span data-ttu-id="38c18-112">**xlHpcRetSuccess** _SessionId_参数是否有效;否则为**xlHpcRetInvalidSessionId**。</span><span class="sxs-lookup"><span data-stu-id="38c18-112">**xlHpcRetSuccess** if the  _SessionId_ argument is valid; otherwise **xlHpcRetInvalidSessionId**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="38c18-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38c18-113">See also</span></span>

- [<span data-ttu-id="38c18-114">OpenSession</span><span class="sxs-lookup"><span data-stu-id="38c18-114">OpenSession</span></span>](opensession.md)
- [<span data-ttu-id="38c18-115">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="38c18-115">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

