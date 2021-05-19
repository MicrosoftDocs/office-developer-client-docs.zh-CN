---
title: CancelOutstandingRequests
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0de9d4e2-eb3f-40e7-aa24-f430892eb9ec
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 882458ab096cbced8e0635dab65fe0b1d680388f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414716"
---
# <a name="canceloutstandingrequests"></a><span data-ttu-id="3e489-103">CancelOutstandingRequests</span><span class="sxs-lookup"><span data-stu-id="3e489-103">CancelOutstandingRequests</span></span>

<span data-ttu-id="3e489-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3e489-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="3e489-105">通知群集连接器已取消 Excel 计算，因此该会话内的所有待定函数调用可能也被取消 (并且 Excel 不需要具有其结果) 的回调。</span><span class="sxs-lookup"><span data-stu-id="3e489-105">Informs the cluster connector that an Excel calculation has been canceled, and therefore all pending function calls within that session may be cancelled as well (and that Excel does not expect callbacks with their results).</span></span>
  
```cpp
int CancelOutstandingRequests(int SessionId)
```

## <a name="parameters"></a><span data-ttu-id="3e489-106">参数</span><span class="sxs-lookup"><span data-stu-id="3e489-106">Parameters</span></span>

<span data-ttu-id="3e489-107">_SessionID_</span><span class="sxs-lookup"><span data-stu-id="3e489-107">_SessionID_</span></span>
  
> <span data-ttu-id="3e489-108">已取消计算使用的会话的 ID。</span><span class="sxs-lookup"><span data-stu-id="3e489-108">The ID of the session used by the canceled calculation.</span></span> <span data-ttu-id="3e489-109">此值与 [OpenSession 返回的值匹配](opensession.md)。</span><span class="sxs-lookup"><span data-stu-id="3e489-109">This value matches the value returned by [OpenSession](opensession.md).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3e489-110">返回值</span><span class="sxs-lookup"><span data-stu-id="3e489-110">Return value</span></span>

<span data-ttu-id="3e489-111">**xlHpcRetSuccess（** 如果 _SessionId_ 参数有效）;**xlHpcRetInvalidSessionId** 如果 _SessionId_ 参数无效;**其他故障时为 xlHpcRetCallFailed。**</span><span class="sxs-lookup"><span data-stu-id="3e489-111">**xlHpcRetSuccess** if the  _SessionId_ argument is valid; **xlHpcRetInvalidSessionId** if the  _SessionId_ argument is invalid; **xlHpcRetCallFailed** on other failures.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="3e489-112">备注</span><span class="sxs-lookup"><span data-stu-id="3e489-112">Remarks</span></span>

<span data-ttu-id="3e489-113">实现者应停止会话的所有进程，以提高性能，因为在此调用后收到的任何结果将被Excel。</span><span class="sxs-lookup"><span data-stu-id="3e489-113">Implementers should stop all processes for the session for improved performance, as any results received after this call will be discarded by Excel.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3e489-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e489-114">See also</span></span>

- [<span data-ttu-id="3e489-115">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="3e489-115">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

