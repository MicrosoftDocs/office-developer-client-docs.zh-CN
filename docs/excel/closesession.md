---
title: CloseSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2c2371c8-b0e0-4992-b7ac-3949eadf1ebe
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: af8f7398ed9d5edfbf1615930874a800d8835487
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773644"
---
# <a name="closesession"></a><span data-ttu-id="578f8-103">CloseSession</span><span class="sxs-lookup"><span data-stu-id="578f8-103">CloseSession</span></span>

<span data-ttu-id="578f8-104">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="578f8-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="578f8-105">结束与群集的会话。</span><span class="sxs-lookup"><span data-stu-id="578f8-105">Ends a session with a cluster.</span></span>
  
```cpp
int CloseSession(int SessionId)
```

## <a name="parameters"></a><span data-ttu-id="578f8-106">参数</span><span class="sxs-lookup"><span data-stu-id="578f8-106">Parameters</span></span>

<span data-ttu-id="578f8-107">_SessionId_</span><span class="sxs-lookup"><span data-stu-id="578f8-107">_SessionId_</span></span>
  
> <span data-ttu-id="578f8-108">要关闭的会话 ID。</span><span class="sxs-lookup"><span data-stu-id="578f8-108">The ID of the session to close.</span></span> <span data-ttu-id="578f8-109">此值必须匹配[OpenSession](opensession.md)返回的值。</span><span class="sxs-lookup"><span data-stu-id="578f8-109">This value must match the value returned by [OpenSession](opensession.md).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="578f8-110">返回值</span><span class="sxs-lookup"><span data-stu-id="578f8-110">Return value</span></span>

<span data-ttu-id="578f8-111">**xlHpcRetSuccess**会话关闭; 如果**xlHpcRetInvalidSessionId** _SessionId_参数无效; 如果有关其他故障**xlHpcRetCallFailed** 。</span><span class="sxs-lookup"><span data-stu-id="578f8-111">**xlHpcRetSuccess** if the session closed; **xlHpcRetInvalidSessionId** if the  _SessionId_ argument is invalid; **xlHpcRetCallFailed** on other failures.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="578f8-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="578f8-112">See also</span></span>

- [<span data-ttu-id="578f8-113">OpenSession</span><span class="sxs-lookup"><span data-stu-id="578f8-113">OpenSession</span></span>](opensession.md)
- [<span data-ttu-id="578f8-114">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="578f8-114">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

