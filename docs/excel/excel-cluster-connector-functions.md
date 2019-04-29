---
title: Excel 群集连接器函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 65927ef9-29f7-499a-a1c1-6f672c09bb6b
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 41a5cf1ecb7c8f38f4aa5b62a493b3f45c2fe090
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408584"
---
# <a name="excel-cluster-connector-functions"></a><span data-ttu-id="88693-103">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="88693-103">Excel Cluster Connector Functions</span></span>

 <span data-ttu-id="88693-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="88693-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="88693-105">Microsoft Excel 2013 群集连接器 dll 必须实现本节中所述的函数。</span><span class="sxs-lookup"><span data-stu-id="88693-105">Microsoft Excel 2013 cluster connector DLLs must implement the functions described in this section.</span></span>
  
<span data-ttu-id="88693-106">本节的参考主题中提到的返回值在 SDK 包含文件 xlcall.h 中进行定义。</span><span class="sxs-lookup"><span data-stu-id="88693-106">The return values mentioned in reference topics in this section are defined in the SDK include file, xlcall.h.</span></span>
  
## <a name="cluster-connector-architecture"></a><span data-ttu-id="88693-107">群集连接器体系结构</span><span class="sxs-lookup"><span data-stu-id="88693-107">Cluster Connector Architecture</span></span>

<span data-ttu-id="88693-108">Excel 将调用群集连接器中的入口点, 以将用户定义的函数调用传输到高性能计算群集, 并将其用于群集会话管理。</span><span class="sxs-lookup"><span data-stu-id="88693-108">Excel calls entry points in a cluster connector to transfer user-defined function calls to a high-performance compute cluster, and for cluster session management.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="88693-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="88693-109">In this section</span></span>

[<span data-ttu-id="88693-110">CallUDF</span><span class="sxs-lookup"><span data-stu-id="88693-110">CallUDF</span></span>](calludf.md)
  
[<span data-ttu-id="88693-111">CancelOutstandingRequests</span><span class="sxs-lookup"><span data-stu-id="88693-111">CancelOutstandingRequests</span></span>](canceloutstandingrequests.md)
  
[<span data-ttu-id="88693-112">CloseSession</span><span class="sxs-lookup"><span data-stu-id="88693-112">CloseSession</span></span>](closesession.md)
  
[<span data-ttu-id="88693-113">OpenSession</span><span class="sxs-lookup"><span data-stu-id="88693-113">OpenSession</span></span>](opensession.md)
  
[<span data-ttu-id="88693-114">PingSession</span><span class="sxs-lookup"><span data-stu-id="88693-114">PingSession</span></span>](pingsession.md)
  
[<span data-ttu-id="88693-115">ShowOptions</span><span class="sxs-lookup"><span data-stu-id="88693-115">ShowOptions</span></span>](showoptions.md)
  
## <a name="see-also"></a><span data-ttu-id="88693-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88693-116">See also</span></span>



[<span data-ttu-id="88693-117">Developing Excel Cluster Connectors</span><span class="sxs-lookup"><span data-stu-id="88693-117">Developing Excel Cluster Connectors</span></span>](developing-excel-cluster-connectors.md)
  
[<span data-ttu-id="88693-118">群集安全函数</span><span class="sxs-lookup"><span data-stu-id="88693-118">Cluster Safe Functions</span></span>](cluster-safe-functions.md)

