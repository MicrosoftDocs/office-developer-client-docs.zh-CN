---
title: Excel群集连接器功能
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
# <a name="excel-cluster-connector-functions"></a><span data-ttu-id="438cb-103">Excel群集连接器功能</span><span class="sxs-lookup"><span data-stu-id="438cb-103">Excel Cluster Connector Functions</span></span>

 <span data-ttu-id="438cb-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="438cb-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="438cb-105">Microsoft Excel 2013群集连接器 DLL 必须实现本节中所述的功能。</span><span class="sxs-lookup"><span data-stu-id="438cb-105">Microsoft Excel 2013 cluster connector DLLs must implement the functions described in this section.</span></span>
  
<span data-ttu-id="438cb-106">本节参考主题中提到的返回值在 SDK include 文件 xlcall.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="438cb-106">The return values mentioned in reference topics in this section are defined in the SDK include file, xlcall.h.</span></span>
  
## <a name="cluster-connector-architecture"></a><span data-ttu-id="438cb-107">群集连接器体系结构</span><span class="sxs-lookup"><span data-stu-id="438cb-107">Cluster Connector Architecture</span></span>

<span data-ttu-id="438cb-108">Excel调用群集连接器中的入口点，以将用户定义函数调用转移到高性能计算群集以及用于群集会话管理。</span><span class="sxs-lookup"><span data-stu-id="438cb-108">Excel calls entry points in a cluster connector to transfer user-defined function calls to a high-performance compute cluster, and for cluster session management.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="438cb-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="438cb-109">In this section</span></span>

[<span data-ttu-id="438cb-110">CallUDF</span><span class="sxs-lookup"><span data-stu-id="438cb-110">CallUDF</span></span>](calludf.md)
  
[<span data-ttu-id="438cb-111">CancelOutstandingRequests</span><span class="sxs-lookup"><span data-stu-id="438cb-111">CancelOutstandingRequests</span></span>](canceloutstandingrequests.md)
  
[<span data-ttu-id="438cb-112">CloseSession</span><span class="sxs-lookup"><span data-stu-id="438cb-112">CloseSession</span></span>](closesession.md)
  
[<span data-ttu-id="438cb-113">OpenSession</span><span class="sxs-lookup"><span data-stu-id="438cb-113">OpenSession</span></span>](opensession.md)
  
[<span data-ttu-id="438cb-114">PingSession</span><span class="sxs-lookup"><span data-stu-id="438cb-114">PingSession</span></span>](pingsession.md)
  
[<span data-ttu-id="438cb-115">ShowOptions</span><span class="sxs-lookup"><span data-stu-id="438cb-115">ShowOptions</span></span>](showoptions.md)
  
## <a name="see-also"></a><span data-ttu-id="438cb-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="438cb-116">See also</span></span>



[<span data-ttu-id="438cb-117">Developing Excel Cluster Connectors</span><span class="sxs-lookup"><span data-stu-id="438cb-117">Developing Excel Cluster Connectors</span></span>](developing-excel-cluster-connectors.md)
  
[<span data-ttu-id="438cb-118">群集安全函数</span><span class="sxs-lookup"><span data-stu-id="438cb-118">Cluster Safe Functions</span></span>](cluster-safe-functions.md)

