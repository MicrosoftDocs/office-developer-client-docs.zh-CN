---
title: CloseSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2c2371c8-b0e0-4992-b7ac-3949eadf1ebe
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 9186fb14c33d507b8c9ae709a67f1b43e6206d5b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422535"
---
# <a name="closesession"></a><span data-ttu-id="d24f9-103">CloseSession</span><span class="sxs-lookup"><span data-stu-id="d24f9-103">CloseSession</span></span>

<span data-ttu-id="d24f9-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d24f9-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="d24f9-105">结束与群集的会话。</span><span class="sxs-lookup"><span data-stu-id="d24f9-105">Ends a session with a cluster.</span></span>
  
```cpp
int CloseSession(int SessionId)
```

## <a name="parameters"></a><span data-ttu-id="d24f9-106">参数</span><span class="sxs-lookup"><span data-stu-id="d24f9-106">Parameters</span></span>

<span data-ttu-id="d24f9-107">_SessionId_</span><span class="sxs-lookup"><span data-stu-id="d24f9-107">_SessionId_</span></span>
  
> <span data-ttu-id="d24f9-108">要关闭的会话的 ID。</span><span class="sxs-lookup"><span data-stu-id="d24f9-108">The ID of the session to close.</span></span> <span data-ttu-id="d24f9-109">此值必须与 [OpenSession 返回的值匹配](opensession.md)。</span><span class="sxs-lookup"><span data-stu-id="d24f9-109">This value must match the value returned by [OpenSession](opensession.md).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d24f9-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d24f9-110">Return value</span></span>

<span data-ttu-id="d24f9-111">**xlHpcRetSuccess（** 如果会话已关闭）;**xlHpcRetInvalidSessionId** 如果 _SessionId_ 参数无效;**其他故障时为 xlHpcRetCallFailed。**</span><span class="sxs-lookup"><span data-stu-id="d24f9-111">**xlHpcRetSuccess** if the session closed; **xlHpcRetInvalidSessionId** if the  _SessionId_ argument is invalid; **xlHpcRetCallFailed** on other failures.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d24f9-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d24f9-112">See also</span></span>

- [<span data-ttu-id="d24f9-113">OpenSession</span><span class="sxs-lookup"><span data-stu-id="d24f9-113">OpenSession</span></span>](opensession.md)
- [<span data-ttu-id="d24f9-114">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="d24f9-114">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

