---
title: Server 属性 (RDS)
TOCTitle: Server property (RDS)
ms:assetid: 17519dbe-a43a-1d0d-22c1-dc0def2f63ab
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248926(v=office.15)
ms:contentKeyID: 48543448
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4f35910591d86e0e5a2b92d680be3c5f64504088
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308685"
---
# <a name="server-property-rds"></a><span data-ttu-id="a8be9-102">Server 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="a8be9-102">Server property (RDS)</span></span>

<span data-ttu-id="a8be9-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="a8be9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a8be9-104">指示 Internet 信息服务 (IIS) 名称和通信协议。</span><span class="sxs-lookup"><span data-stu-id="a8be9-104">Indicates the Internet Information Services (IIS) name and communication protocol.</span></span>

<span data-ttu-id="a8be9-105">可以在设计时在 [RDS.DataControl](datacontrol-object-rds.md) 对象的 OBJECT 标记中设置 **Server** 属性，也可以在运行时在脚本代码中进行设置。</span><span class="sxs-lookup"><span data-stu-id="a8be9-105">You can set the **Server** property at design time in the [RDS.DataControl](datacontrol-object-rds.md) object's OBJECT tags, or at run time in scripting code.</span></span>

## <a name="syntax"></a><span data-ttu-id="a8be9-106">语法</span><span class="sxs-lookup"><span data-stu-id="a8be9-106">Syntax</span></span>

|<span data-ttu-id="a8be9-107">协议</span><span class="sxs-lookup"><span data-stu-id="a8be9-107">Protocol</span></span>|<span data-ttu-id="a8be9-108">设计时语法</span><span class="sxs-lookup"><span data-stu-id="a8be9-108">Design-time syntax</span></span>|
|:-------|:-----------------|
|<span data-ttu-id="a8be9-109">http.sys</span><span class="sxs-lookup"><span data-stu-id="a8be9-109">HTTP</span></span>|`<PARAM NAME="Server" VALUE="https://awebsrvr:port">`|
|<span data-ttu-id="a8be9-110">ip-https</span><span class="sxs-lookup"><span data-stu-id="a8be9-110">HTTPS</span></span>|`<PARAM NAME="Server" VALUE="https://awebsrvr:port">`|
|<span data-ttu-id="a8be9-111">封锁</span><span class="sxs-lookup"><span data-stu-id="a8be9-111">DCOM</span></span>|`<PARAM NAME="Server" VALUE="computername">`|
|<span data-ttu-id="a8be9-112">进程内</span><span class="sxs-lookup"><span data-stu-id="a8be9-112">In-process</span></span>|`<PARAM NAME="Server" VALUE="">`|


|<span data-ttu-id="a8be9-113">协议</span><span class="sxs-lookup"><span data-stu-id="a8be9-113">Protocol</span></span>|<span data-ttu-id="a8be9-114">运行时语法</span><span class="sxs-lookup"><span data-stu-id="a8be9-114">Run-time syntax</span></span>|
|:-------|:--------------|
|<span data-ttu-id="a8be9-115">http.sys</span><span class="sxs-lookup"><span data-stu-id="a8be9-115">HTTP</span></span>|`DataControl.Server="https://awebsrvr:port"`|
|<span data-ttu-id="a8be9-116">ip-https</span><span class="sxs-lookup"><span data-stu-id="a8be9-116">HTTPS</span></span>|`DataControl.Server="https://awebsrvr:port"`|
|<span data-ttu-id="a8be9-117">封锁</span><span class="sxs-lookup"><span data-stu-id="a8be9-117">DCOM</span></span>|`DataControl.Server="computername"`|
|<span data-ttu-id="a8be9-118">进程内</span><span class="sxs-lookup"><span data-stu-id="a8be9-118">In-process</span></span>|`DataControl.Server=""`|


## <a name="parameters"></a><span data-ttu-id="a8be9-119">参数</span><span class="sxs-lookup"><span data-stu-id="a8be9-119">Parameters</span></span>

|<span data-ttu-id="a8be9-120">参数</span><span class="sxs-lookup"><span data-stu-id="a8be9-120">Parameter</span></span>|<span data-ttu-id="a8be9-121">描述</span><span class="sxs-lookup"><span data-stu-id="a8be9-121">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="a8be9-122">*awebsrvr* 或 *computername*</span><span class="sxs-lookup"><span data-stu-id="a8be9-122">*awebsrvr* or *computername*</span></span> |<span data-ttu-id="a8be9-123">一个包含 Internet 或 Intranet 路径的 **String** 值，如果服务器位于远程计算机上，则为计算机名；如果服务器位于本地计算机上，则为空字符串。</span><span class="sxs-lookup"><span data-stu-id="a8be9-123">A **String** value that contains an Internet or intranet path, or computer name, if the server is on a remote computer; or, an empty string if the server is on the local computer.</span></span>|
|<span data-ttu-id="a8be9-124">*端口*</span><span class="sxs-lookup"><span data-stu-id="a8be9-124">*port*</span></span> |<span data-ttu-id="a8be9-p101">Optional. A port that is used to connect to an IIS server. The port number is set in Internet Explorer (on the **Tools** menu, click **Internet Options**, and then select the **Connection** tab) or in IIS.</span><span class="sxs-lookup"><span data-stu-id="a8be9-p101">Optional. A port that is used to connect to an IIS server. The port number is set in Internet Explorer (on the **Tools** menu, click **Internet Options**, and then select the **Connection** tab) or in IIS.</span></span>|
|<span data-ttu-id="a8be9-128">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="a8be9-128">*DataControl*</span></span> |<span data-ttu-id="a8be9-129">一个代表 **RDS.DataControl** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="a8be9-129">An object variable that represents an **RDS.DataControl** object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a8be9-130">注解</span><span class="sxs-lookup"><span data-stu-id="a8be9-130">Remarks</span></span>

<span data-ttu-id="a8be9-131">服务器是处理 **RDS.DataControl** 请求（即查询或更新）的位置。</span><span class="sxs-lookup"><span data-stu-id="a8be9-131">The server is the location where the **RDS.DataControl** request (that is, a query or update) is processed.</span></span> <span data-ttu-id="a8be9-132">默认情况下，所有请求均由 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象、[MSDFMAP.Handler](datafactory-customization.md) 组件以及指定的服务器上的 [MSDFMAP.INI](understanding-the-customization-file.md) 文件进行处理。</span><span class="sxs-lookup"><span data-stu-id="a8be9-132">By default, all requests are processed by the [RDSServer.DataFactory](datafactory-object-rdsserver.md) object, [MSDFMAP.Handler](datafactory-customization.md) component, and [MSDFMAP.INI](understanding-the-customization-file.md) file on the specified server.</span></span> 

<span data-ttu-id="a8be9-133">在更换服务器时应记住这一点，以便调整新旧 **MSDFMAP.INI** 文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="a8be9-133">Remember that when changing servers to reconcile settings in the old and new **MSDFMAP.INI** files.</span></span> <span data-ttu-id="a8be9-134">不兼容会导致在一台服务器上成功处理的请求在另一台服务器上失败。</span><span class="sxs-lookup"><span data-stu-id="a8be9-134">Incompatibilities may cause requests that succeed on one server to fail on another.</span></span> <span data-ttu-id="a8be9-135">如果 Server 属性设置为 ""，则将在本地计算机上使用这些对象。</span><span class="sxs-lookup"><span data-stu-id="a8be9-135">If the Server property is set to "", these objects will be used on the local machine.</span></span>

