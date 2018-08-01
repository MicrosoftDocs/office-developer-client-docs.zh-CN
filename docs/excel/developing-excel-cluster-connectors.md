---
title: 开发 Excel 群集连接器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: b538ae44-37d2-496b-b6e7-b0e39f6e38cb
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 8c9a166ac06685c0a450e1e0bd60b2fbef67d336
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773632"
---
# <a name="developing-excel-cluster-connectors"></a><span data-ttu-id="63249-103">开发 Excel 群集连接器</span><span class="sxs-lookup"><span data-stu-id="63249-103">Developing Excel Cluster Connectors</span></span>

<span data-ttu-id="63249-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63249-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="63249-105">Excel 群集连接器的自动卸载用户定义的群集安全函数调用中 XLL 群集服务器提供一种方法。</span><span class="sxs-lookup"><span data-stu-id="63249-105">Excel cluster connectors provide a means for automatically offloading cluster-safe user-defined function calls in an XLL to a clustered server.</span></span> <span data-ttu-id="63249-106">群集安全用户定义函数的说明，请参阅[群集安全函数](cluster-safe-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="63249-106">For a description of cluster-safe user-defined functions, see [Cluster Safe Functions](cluster-safe-functions.md).</span></span> <span data-ttu-id="63249-107">此卸载可以通过启用详细计算的资源用于提高性能。</span><span class="sxs-lookup"><span data-stu-id="63249-107">This offloading can improve performance by enabling more computing resources to be used.</span></span> <span data-ttu-id="63249-108">群集连接器通常是由高性能计算群集供应商开发。</span><span class="sxs-lookup"><span data-stu-id="63249-108">A cluster connector is typically developed by a high performance compute cluster vendor.</span></span>
  
## <a name="cluster-connectors"></a><span data-ttu-id="63249-109">群集连接器</span><span class="sxs-lookup"><span data-stu-id="63249-109">Cluster Connectors</span></span>

<span data-ttu-id="63249-110">群集连接器是 DLL 提供定义的入口点，Excel 用来协调群集安全用户定义函数调用。</span><span class="sxs-lookup"><span data-stu-id="63249-110">A cluster connector is a DLL that provides defined entry points that Excel uses to coordinate cluster-safe user-defined function calls.</span></span> <span data-ttu-id="63249-111">会话管理，使函数调用 （通过将传递的完全限定的函数名称和调用的实际参数），以及呼叫结果返回到 Excel 通过充当 Excel 和高性能计算群集，之间的接口回调机制。</span><span class="sxs-lookup"><span data-stu-id="63249-111">It serves as an interface between Excel and the high-performance compute cluster, for session management, for making function calls (by passing the fully-qualified function name and the call's actual arguments), and for returning call results to Excel through a callback mechanism.</span></span>
  
<span data-ttu-id="63249-112">若要创建群集连接器，请创建 DLL 公开[Excel 群集连接器函数](excel-cluster-connector-functions.md)中列出的入口点。</span><span class="sxs-lookup"><span data-stu-id="63249-112">To create a cluster connector, create a DLL that exposes the entry points listed in [Excel Cluster Connector Functions](excel-cluster-connector-functions.md).</span></span>
  
## <a name="installing-a-cluster-connector"></a><span data-ttu-id="63249-113">安装群集连接器</span><span class="sxs-lookup"><span data-stu-id="63249-113">Installing a Cluster Connector</span></span>

<span data-ttu-id="63249-114">使群集连接器在 Excel 中可用，连接器的安装程序代码必须安装 Excel 的计算机上安装的 DLL 的连接器。</span><span class="sxs-lookup"><span data-stu-id="63249-114">To make a cluster connector available in Excel, the setup code of the connector must install the DLL of the connector on the computer where Excel is installed.</span></span> <span data-ttu-id="63249-115">此外，连接器的安装程序代码必须添加以下注册表项下连接器条目：</span><span class="sxs-lookup"><span data-stu-id="63249-115">In addition, the setup code of the connector must add an entry for the connector under the following registry key:</span></span>
  
<span data-ttu-id="63249-116">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\Excel\Excel 群集 Connectors\\</span><span class="sxs-lookup"><span data-stu-id="63249-116">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\Excel\Excel Cluster Connectors\\</span></span>
  
<span data-ttu-id="63249-117">将节点添加到此密钥的群集连接器，指定以下字符串：</span><span class="sxs-lookup"><span data-stu-id="63249-117">Add a node to this key for the cluster connector that specifies the following strings:</span></span>
  
-  <span data-ttu-id="63249-118">`Name`— 将出现在 Excel 中的群集连接器的列表的名称。</span><span class="sxs-lookup"><span data-stu-id="63249-118">`Name`—the name that will appear in the list of cluster connectors in Excel.</span></span>
    
-  <span data-ttu-id="63249-119">`Filename`— DLL 的完整路径。</span><span class="sxs-lookup"><span data-stu-id="63249-119">`Filename`—the full path for the DLL.</span></span>
    

