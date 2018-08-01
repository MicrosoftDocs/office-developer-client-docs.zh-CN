---
title: OpenSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6cfd3513-800f-4602-b3e6-6430920718d6
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 782843f11643e203488b313181d224443a1d36c5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773807"
---
# <a name="opensession"></a><span data-ttu-id="e04f6-103">OpenSession</span><span class="sxs-lookup"><span data-stu-id="e04f6-103">OpenSession</span></span>

<span data-ttu-id="e04f6-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e04f6-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="e04f6-105">创建可在其中执行用户定义函数的会话。</span><span class="sxs-lookup"><span data-stu-id="e04f6-105">Creates a session in which user-defined functions can be executed.</span></span>
  
```cpp
int OpenSession(WCHAR *Params)
```

## <a name="parameters"></a><span data-ttu-id="e04f6-106">参数</span><span class="sxs-lookup"><span data-stu-id="e04f6-106">Parameters</span></span>

<span data-ttu-id="e04f6-107">_参数_</span><span class="sxs-lookup"><span data-stu-id="e04f6-107">_Params_</span></span>
  
> <span data-ttu-id="e04f6-108">一个指向以分号分隔的会话的参数的 UNICODE 字符串。</span><span class="sxs-lookup"><span data-stu-id="e04f6-108">A pointer to semicolon-delimited UNICODE string of parameters for the session.</span></span> <span data-ttu-id="e04f6-109">Excel 不使用此参数。</span><span class="sxs-lookup"><span data-stu-id="e04f6-109">Excel does not use this argument.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e04f6-110">返回值</span><span class="sxs-lookup"><span data-stu-id="e04f6-110">Return value</span></span>

<span data-ttu-id="e04f6-111">要会话已成功创建; 如果在到群集连接器，而其他呼叫中使用的会话 ID否则为**xlHpcRetCallFailed**。</span><span class="sxs-lookup"><span data-stu-id="e04f6-111">A session ID to use in other calls to the cluster connector, if the session was successfully created; otherwise **xlHpcRetCallFailed**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e04f6-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e04f6-112">See also</span></span>

- [<span data-ttu-id="e04f6-113">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="e04f6-113">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

