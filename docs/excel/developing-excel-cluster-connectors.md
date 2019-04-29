---
title: 开发 Excel 群集连接器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: b538ae44-37d2-496b-b6e7-b0e39f6e38cb
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e1c70713586a7a143f119a2c3e9d34b982dcedba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412595"
---
# <a name="developing-excel-cluster-connectors"></a><span data-ttu-id="94d29-103">开发 Excel 群集连接器</span><span class="sxs-lookup"><span data-stu-id="94d29-103">Developing Excel Cluster Connectors</span></span>

<span data-ttu-id="94d29-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94d29-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="94d29-105">Excel 群集连接器提供了一种方法, 用于将 XLL 中的群集安全用户定义的函数调用自动卸载到群集服务器。</span><span class="sxs-lookup"><span data-stu-id="94d29-105">Excel cluster connectors provide a means for automatically offloading cluster-safe user-defined function calls in an XLL to a clustered server.</span></span> <span data-ttu-id="94d29-106">有关群集安全用户定义的函数的说明, 请参阅[群集安全函数](cluster-safe-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="94d29-106">For a description of cluster-safe user-defined functions, see [Cluster Safe Functions](cluster-safe-functions.md).</span></span> <span data-ttu-id="94d29-107">此卸载可以通过启用更多的计算资源来提高性能。</span><span class="sxs-lookup"><span data-stu-id="94d29-107">This offloading can improve performance by enabling more computing resources to be used.</span></span> <span data-ttu-id="94d29-108">群集连接器通常由高性能计算群集供应商开发。</span><span class="sxs-lookup"><span data-stu-id="94d29-108">A cluster connector is typically developed by a high performance compute cluster vendor.</span></span>
  
## <a name="cluster-connectors"></a><span data-ttu-id="94d29-109">群集连接器</span><span class="sxs-lookup"><span data-stu-id="94d29-109">Cluster Connectors</span></span>

<span data-ttu-id="94d29-110">群集连接器是提供定义的入口点的 DLL, Excel 使用这些入口点来协调群集安全用户定义的函数调用。</span><span class="sxs-lookup"><span data-stu-id="94d29-110">A cluster connector is a DLL that provides defined entry points that Excel uses to coordinate cluster-safe user-defined function calls.</span></span> <span data-ttu-id="94d29-111">它充当 excel 和高性能计算群集之间的接口, 用于实现函数调用 (通过传递完全限定的函数名称和调用的实际参数), 以及将呼叫结果返回到 Excel 的过程回调机制。</span><span class="sxs-lookup"><span data-stu-id="94d29-111">It serves as an interface between Excel and the high-performance compute cluster, for session management, for making function calls (by passing the fully-qualified function name and the call's actual arguments), and for returning call results to Excel through a callback mechanism.</span></span>
  
<span data-ttu-id="94d29-112">若要创建群集连接器, 请创建一个 DLL, 用于公开在[Excel 群集连接器函数](excel-cluster-connector-functions.md)中列出的入口点。</span><span class="sxs-lookup"><span data-stu-id="94d29-112">To create a cluster connector, create a DLL that exposes the entry points listed in [Excel Cluster Connector Functions](excel-cluster-connector-functions.md).</span></span>
  
## <a name="installing-a-cluster-connector"></a><span data-ttu-id="94d29-113">安装群集连接器</span><span class="sxs-lookup"><span data-stu-id="94d29-113">Installing a Cluster Connector</span></span>

<span data-ttu-id="94d29-114">若要使群集连接器在 excel 中可用, 连接器的安装代码必须在安装了 excel 的计算机上安装连接器的 DLL。</span><span class="sxs-lookup"><span data-stu-id="94d29-114">To make a cluster connector available in Excel, the setup code of the connector must install the DLL of the connector on the computer where Excel is installed.</span></span> <span data-ttu-id="94d29-115">此外, 连接器的安装程序代码必须在以下注册表项下添加连接器的条目:</span><span class="sxs-lookup"><span data-stu-id="94d29-115">In addition, the setup code of the connector must add an entry for the connector under the following registry key:</span></span>
  
<span data-ttu-id="94d29-116">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\Excel\Excel 群集连接器 \\</span><span class="sxs-lookup"><span data-stu-id="94d29-116">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\Excel\Excel Cluster Connectors\\</span></span>
  
<span data-ttu-id="94d29-117">将节点添加到指定以下字符串的群集连接器的此项中:</span><span class="sxs-lookup"><span data-stu-id="94d29-117">Add a node to this key for the cluster connector that specifies the following strings:</span></span>
  
-  <span data-ttu-id="94d29-118">`Name`—将显示在 Excel 中的群集连接器列表中的名称。</span><span class="sxs-lookup"><span data-stu-id="94d29-118">`Name`—the name that will appear in the list of cluster connectors in Excel.</span></span>
    
-  <span data-ttu-id="94d29-119">`Filename`— DLL 的完整路径。</span><span class="sxs-lookup"><span data-stu-id="94d29-119">`Filename`—the full path for the DLL.</span></span>
    

