---
title: CancelOutstandingRequests
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0de9d4e2-eb3f-40e7-aa24-f430892eb9ec
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 65d4257037b18c8fa68cabe0c08091ec67343fa5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773634"
---
# <a name="canceloutstandingrequests"></a><span data-ttu-id="c3b22-103">CancelOutstandingRequests</span><span class="sxs-lookup"><span data-stu-id="c3b22-103">CancelOutstandingRequests</span></span>

<span data-ttu-id="c3b22-104">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c3b22-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="c3b22-105">通知的 Excel 计算已被取消，因此所有挂起的会话中的函数调用可能会取消以及群集连接器 （和 Excel 并不需要其结果的回调）。</span><span class="sxs-lookup"><span data-stu-id="c3b22-105">Informs the cluster connector that an Excel calculation has been canceled, and therefore all pending function calls within that session may be cancelled as well (and that Excel does not expect callbacks with their results).</span></span>
  
```cpp
int CancelOutstandingRequests(int SessionId)
```

## <a name="parameters"></a><span data-ttu-id="c3b22-106">参数</span><span class="sxs-lookup"><span data-stu-id="c3b22-106">Parameters</span></span>

<span data-ttu-id="c3b22-107">_SessionID_</span><span class="sxs-lookup"><span data-stu-id="c3b22-107">_SessionID_</span></span>
  
> <span data-ttu-id="c3b22-108">使用已取消计算会话的 ID。</span><span class="sxs-lookup"><span data-stu-id="c3b22-108">The ID of the session used by the canceled calculation.</span></span> <span data-ttu-id="c3b22-109">此值匹配[OpenSession](opensession.md)返回的值。</span><span class="sxs-lookup"><span data-stu-id="c3b22-109">This value matches the value returned by [OpenSession](opensession.md).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c3b22-110">返回值</span><span class="sxs-lookup"><span data-stu-id="c3b22-110">Return value</span></span>

<span data-ttu-id="c3b22-111">**xlHpcRetSuccess** _SessionId_参数是否有效;**xlHpcRetInvalidSessionId** _SessionId_参数无效; 如果有关其他故障**xlHpcRetCallFailed** 。</span><span class="sxs-lookup"><span data-stu-id="c3b22-111">**xlHpcRetSuccess** if the  _SessionId_ argument is valid; **xlHpcRetInvalidSessionId** if the  _SessionId_ argument is invalid; **xlHpcRetCallFailed** on other failures.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c3b22-112">备注</span><span class="sxs-lookup"><span data-stu-id="c3b22-112">Remarks</span></span>

<span data-ttu-id="c3b22-113">实施应以提高性能，作为此呼叫将被丢弃由 Excel 之后收到任何结果会话停止所有进程。</span><span class="sxs-lookup"><span data-stu-id="c3b22-113">Implementers should stop all processes for the session for improved performance, as any results received after this call will be discarded by Excel.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c3b22-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3b22-114">See also</span></span>

- [<span data-ttu-id="c3b22-115">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="c3b22-115">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

