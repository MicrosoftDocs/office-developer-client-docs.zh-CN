---
title: OpenSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6cfd3513-800f-4602-b3e6-6430920718d6
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3e4df0c5772f28ab4ab8d84eaddfe4409a88061b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421835"
---
# <a name="opensession"></a><span data-ttu-id="4b757-103">OpenSession</span><span class="sxs-lookup"><span data-stu-id="4b757-103">OpenSession</span></span>

<span data-ttu-id="4b757-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4b757-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="4b757-105">创建可在其中执行用户定义函数的会话。</span><span class="sxs-lookup"><span data-stu-id="4b757-105">Creates a session in which user-defined functions can be executed.</span></span>
  
```cpp
int OpenSession(WCHAR *Params)
```

## <a name="parameters"></a><span data-ttu-id="4b757-106">参数</span><span class="sxs-lookup"><span data-stu-id="4b757-106">Parameters</span></span>

<span data-ttu-id="4b757-107">_参数_</span><span class="sxs-lookup"><span data-stu-id="4b757-107">_Params_</span></span>
  
> <span data-ttu-id="4b757-108">指向会话的参数的以分号分隔的 UNICODE 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="4b757-108">A pointer to semicolon-delimited UNICODE string of parameters for the session.</span></span> <span data-ttu-id="4b757-109">Excel 不使用此参数。</span><span class="sxs-lookup"><span data-stu-id="4b757-109">Excel does not use this argument.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4b757-110">返回值</span><span class="sxs-lookup"><span data-stu-id="4b757-110">Return value</span></span>

<span data-ttu-id="4b757-111">在对群集连接器的其他调用中使用的会话 ID (如果已成功创建会话);否则**xlHpcRetCallFailed**。</span><span class="sxs-lookup"><span data-stu-id="4b757-111">A session ID to use in other calls to the cluster connector, if the session was successfully created; otherwise **xlHpcRetCallFailed**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4b757-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b757-112">See also</span></span>

- [<span data-ttu-id="4b757-113">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="4b757-113">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

