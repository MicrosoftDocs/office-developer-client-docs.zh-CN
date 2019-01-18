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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710347"
---
# <a name="server-property-rds"></a><span data-ttu-id="c725d-102">Server 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="c725d-102">Server property (RDS)</span></span>

<span data-ttu-id="c725d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c725d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c725d-104">指示 Internet 信息服务 (IIS) 名称和通信协议。</span><span class="sxs-lookup"><span data-stu-id="c725d-104">Indicates the Internet Information Services (IIS) name and communication protocol.</span></span>

<span data-ttu-id="c725d-105">可以在设计时在 **RDS.DataControl** 对象的 OBJECT 标记中设置 [Server](datacontrol-object-rds.md) 属性，也可以在运行时在脚本代码中进行设置。</span><span class="sxs-lookup"><span data-stu-id="c725d-105">You can set the **Server** property at design time in the [RDS.DataControl](datacontrol-object-rds.md) object's OBJECT tags, or at run time in scripting code.</span></span>

## <a name="syntax"></a><span data-ttu-id="c725d-106">语法</span><span class="sxs-lookup"><span data-stu-id="c725d-106">Syntax</span></span>

|<span data-ttu-id="c725d-107">协议</span><span class="sxs-lookup"><span data-stu-id="c725d-107">Protocol</span></span>|<span data-ttu-id="c725d-108">设计时语法</span><span class="sxs-lookup"><span data-stu-id="c725d-108">Design-time syntax</span></span>|
|:-------|:-----------------|
|<span data-ttu-id="c725d-109">HTTP</span><span class="sxs-lookup"><span data-stu-id="c725d-109">HTTP</span></span>|`<PARAM NAME="Server" VALUE="https://awebsrvr:port">`|
|<span data-ttu-id="c725d-110">HTTPS</span><span class="sxs-lookup"><span data-stu-id="c725d-110">HTTPS</span></span>|`<PARAM NAME="Server" VALUE="https://awebsrvr:port">`|
|<span data-ttu-id="c725d-111">DCOM</span><span class="sxs-lookup"><span data-stu-id="c725d-111">DCOM</span></span>|`<PARAM NAME="Server" VALUE="computername">`|
|<span data-ttu-id="c725d-112">In-process</span><span class="sxs-lookup"><span data-stu-id="c725d-112">In-process</span></span>|`<PARAM NAME="Server" VALUE="">`|


|<span data-ttu-id="c725d-113">协议</span><span class="sxs-lookup"><span data-stu-id="c725d-113">Protocol</span></span>|<span data-ttu-id="c725d-114">运行时语法</span><span class="sxs-lookup"><span data-stu-id="c725d-114">Run-time syntax</span></span>|
|:-------|:--------------|
|<span data-ttu-id="c725d-115">HTTP</span><span class="sxs-lookup"><span data-stu-id="c725d-115">HTTP</span></span>|`DataControl.Server="https://awebsrvr:port"`|
|<span data-ttu-id="c725d-116">HTTPS</span><span class="sxs-lookup"><span data-stu-id="c725d-116">HTTPS</span></span>|`DataControl.Server="https://awebsrvr:port"`|
|<span data-ttu-id="c725d-117">DCOM</span><span class="sxs-lookup"><span data-stu-id="c725d-117">DCOM</span></span>|`DataControl.Server="computername"`|
|<span data-ttu-id="c725d-118">In-process</span><span class="sxs-lookup"><span data-stu-id="c725d-118">In-process</span></span>|`DataControl.Server=""`|


## <a name="parameters"></a><span data-ttu-id="c725d-119">参数</span><span class="sxs-lookup"><span data-stu-id="c725d-119">Parameters</span></span>

|<span data-ttu-id="c725d-120">参数</span><span class="sxs-lookup"><span data-stu-id="c725d-120">Parameter</span></span>|<span data-ttu-id="c725d-121">说明</span><span class="sxs-lookup"><span data-stu-id="c725d-121">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="c725d-122">*awebsrvr*或*computername*</span><span class="sxs-lookup"><span data-stu-id="c725d-122">*awebsrvr* or *computername*</span></span> |<span data-ttu-id="c725d-123">一个包含 Internet 或 Intranet 路径的 **String** 值，如果服务器位于远程计算机上，则为计算机名；如果服务器位于本地计算机上，则为空字符串。</span><span class="sxs-lookup"><span data-stu-id="c725d-123">A **String** value that contains an Internet or intranet path, or computer name, if the server is on a remote computer; or, an empty string if the server is on the local computer.</span></span>|
|<span data-ttu-id="c725d-124">*端口*</span><span class="sxs-lookup"><span data-stu-id="c725d-124">*port*</span></span> |<span data-ttu-id="c725d-125">可选。</span><span class="sxs-lookup"><span data-stu-id="c725d-125">Optional.</span></span> <span data-ttu-id="c725d-126">用于连接到的 IIS 服务器的端口。</span><span class="sxs-lookup"><span data-stu-id="c725d-126">A port that is used to connect to an IIS server.</span></span> <span data-ttu-id="c725d-127">在 Internet Explorer 中设置的端口号 （在**工具**菜单中，单击**Internet 选项**，然后选择**连接**选项卡） 或在 IIS 中。</span><span class="sxs-lookup"><span data-stu-id="c725d-127">The port number is set in Internet Explorer (on the **Tools** menu, click **Internet Options**, and then select the **Connection** tab) or in IIS.</span></span>|
|<span data-ttu-id="c725d-128">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="c725d-128">*DataControl*</span></span> |<span data-ttu-id="c725d-129">一个代表 **RDS.DataControl** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="c725d-129">An object variable that represents an **RDS.DataControl** object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c725d-130">说明</span><span class="sxs-lookup"><span data-stu-id="c725d-130">Remarks</span></span>

<span data-ttu-id="c725d-131">服务器是处理 **RDS.DataControl** 请求（即查询或更新）的位置。</span><span class="sxs-lookup"><span data-stu-id="c725d-131">The server is the location where the **RDS.DataControl** request (that is, a query or update) is processed.</span></span> <span data-ttu-id="c725d-132">默认情况下，所有请求均由 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象、 [MSDFMAP.Handler](datafactory-customization.md) 组件以及指定的服务器上的 [MSDFMAP.INI](understanding-the-customization-file.md) 文件进行处理。</span><span class="sxs-lookup"><span data-stu-id="c725d-132">By default, all requests are processed by the [RDSServer.DataFactory](datafactory-object-rdsserver.md) object, [MSDFMAP.Handler](datafactory-customization.md) component, and [MSDFMAP.INI](understanding-the-customization-file.md) file on the specified server.</span></span> 

<span data-ttu-id="c725d-133">在更换服务器时应记住这一点，以便调整新旧 **MSDFMAP.INI** 文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="c725d-133">Remember that when changing servers to reconcile settings in the old and new **MSDFMAP.INI** files.</span></span> <span data-ttu-id="c725d-134">不兼容会导致在一台服务器上成功处理的请求在另一台服务器上失败。</span><span class="sxs-lookup"><span data-stu-id="c725d-134">Incompatibilities may cause requests that succeed on one server to fail on another.</span></span> <span data-ttu-id="c725d-135">如果 Server 属性设置为 ""，则将在本地计算机上使用这些对象。</span><span class="sxs-lookup"><span data-stu-id="c725d-135">If the Server property is set to "", these objects will be used on the local machine.</span></span>

