---
title: Excel 群集连接器函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 65927ef9-29f7-499a-a1c1-6f672c09bb6b
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 4a069aa4ed3ee17320ac65ab793ea8812153cc18
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773669"
---
# <a name="excel-cluster-connector-functions"></a><span data-ttu-id="2fe26-103">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="2fe26-103">Excel Cluster Connector Functions</span></span>

 <span data-ttu-id="2fe26-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2fe26-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="2fe26-105">Microsoft Excel 2013 群集连接器 Dll 必须实现的功能，本节中所述。</span><span class="sxs-lookup"><span data-stu-id="2fe26-105">Microsoft Excel 2013 cluster connector DLLs must implement the functions described in this section.</span></span>
  
<span data-ttu-id="2fe26-106">本节中的主题定义 SDK 中的参考中提到的返回值包括文件、 xlcall.h。</span><span class="sxs-lookup"><span data-stu-id="2fe26-106">The return values mentioned in reference topics in this section are defined in the SDK include file, xlcall.h.</span></span>
  
## <a name="cluster-connector-architecture"></a><span data-ttu-id="2fe26-107">群集连接器体系结构</span><span class="sxs-lookup"><span data-stu-id="2fe26-107">Cluster Connector Architecture</span></span>

<span data-ttu-id="2fe26-108">Excel 群集连接器传输高性能计算群集，和用于群集会话管理的用户定义的函数调用中调用入口点。</span><span class="sxs-lookup"><span data-stu-id="2fe26-108">Excel calls entry points in a cluster connector to transfer user-defined function calls to a high-performance compute cluster, and for cluster session management.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="2fe26-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="2fe26-109">In this section</span></span>

[<span data-ttu-id="2fe26-110">CallUDF</span><span class="sxs-lookup"><span data-stu-id="2fe26-110">CallUDF</span></span>](calludf.md)
  
[<span data-ttu-id="2fe26-111">CancelOutstandingRequests</span><span class="sxs-lookup"><span data-stu-id="2fe26-111">CancelOutstandingRequests</span></span>](canceloutstandingrequests.md)
  
[<span data-ttu-id="2fe26-112">CloseSession</span><span class="sxs-lookup"><span data-stu-id="2fe26-112">CloseSession</span></span>](closesession.md)
  
[<span data-ttu-id="2fe26-113">OpenSession</span><span class="sxs-lookup"><span data-stu-id="2fe26-113">OpenSession</span></span>](opensession.md)
  
[<span data-ttu-id="2fe26-114">PingSession</span><span class="sxs-lookup"><span data-stu-id="2fe26-114">PingSession</span></span>](pingsession.md)
  
[<span data-ttu-id="2fe26-115">ShowOptions</span><span class="sxs-lookup"><span data-stu-id="2fe26-115">ShowOptions</span></span>](showoptions.md)
  
## <a name="see-also"></a><span data-ttu-id="2fe26-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fe26-116">See also</span></span>



[<span data-ttu-id="2fe26-117">Developing Excel Cluster Connectors</span><span class="sxs-lookup"><span data-stu-id="2fe26-117">Developing Excel Cluster Connectors</span></span>](developing-excel-cluster-connectors.md)
  
[<span data-ttu-id="2fe26-118">群集安全函数</span><span class="sxs-lookup"><span data-stu-id="2fe26-118">Cluster Safe Functions</span></span>](cluster-safe-functions.md)

