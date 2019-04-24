---
title: CreateObject 方法 (RDS)
TOCTitle: CreateObject method (RDS)
ms:assetid: 130debe5-31cf-4ab0-5f78-9adaec7d7126
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248905(v=office.15)
ms:contentKeyID: 48543360
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 47ad61495bcc96b3099af6273796626e9442cbf0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295371"
---
# <a name="createobject-method-rds"></a><span data-ttu-id="47763-102">CreateObject 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="47763-102">CreateObject method (RDS)</span></span>

<span data-ttu-id="47763-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="47763-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="47763-p101">用于创建目标业务对象的代理，并返回指向该代理的指针。代理打包数据并将其封送到服务器端存根，用于与业务对象进行通信，以便通过 Internet 发送请求和数据。对于进程内组件对象，不使用代理，而仅提供指向对象的指针。</span><span class="sxs-lookup"><span data-stu-id="47763-p101">Creates the proxy for the target business object and returns a pointer to it. The proxy packages and marshals data to the server-side stub for communications with the business object to send requests and data over the Internet. For in-process component objects, no proxies are used, just a pointer to the object is provided.</span></span>

## <a name="syntax"></a><span data-ttu-id="47763-107">语法</span><span class="sxs-lookup"><span data-stu-id="47763-107">Syntax</span></span>

<span data-ttu-id="47763-108">远程数据服务支持以下协议：HTTP、HTTPS（基于安全套接字层的 HTTP）、DCOM 和进程内。</span><span class="sxs-lookup"><span data-stu-id="47763-108">Remote Data Service supports the following protocols: HTTP, HTTPS (HTTP over Secure Socket Layer), DCOM, and in-process.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="47763-109">协议</span><span class="sxs-lookup"><span data-stu-id="47763-109">Protocol</span></span></p></th>
<th><p><span data-ttu-id="47763-110">语法</span><span class="sxs-lookup"><span data-stu-id="47763-110">Syntax</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47763-111">http.sys</span><span class="sxs-lookup"><span data-stu-id="47763-111">HTTP</span></span></p></td>
<td><p><span data-ttu-id="47763-112">设置<em>对象</em> = 的<em>空间</em>。CreateObject (&quot;<em>ProgId</em>&quot; &quot; <em>https://awebsrvr</em>, &quot;)</span><span class="sxs-lookup"><span data-stu-id="47763-112">Set<em>object</em> = <em>DataSpace</em>.CreateObject(&quot;<em>ProgId</em>&quot;, &quot;<em>https://awebsrvr</em>&quot;)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47763-113">ip-https</span><span class="sxs-lookup"><span data-stu-id="47763-113">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="47763-114">设置<em>对象</em> = 的<em>空间</em>。CreateObject (&quot;<em>ProgId</em>&quot; &quot; <em>https://awebsrvr</em>, &quot;)</span><span class="sxs-lookup"><span data-stu-id="47763-114">Set<em>object</em> = <em>DataSpace</em>.CreateObject(&quot;<em>ProgId</em>&quot;, &quot;<em>https://awebsrvr</em>&quot;)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47763-115">封锁</span><span class="sxs-lookup"><span data-stu-id="47763-115">DCOM</span></span></p></td>
<td><p><span data-ttu-id="47763-116">设置<em>对象</em> = 的<em>空间</em>。CreateObject (&quot;<em>ProgId</em>&quot;, &quot; <em>computername</em>&quot;)</span><span class="sxs-lookup"><span data-stu-id="47763-116">Set<em>object</em> = <em>DataSpace</em>.CreateObject(&quot;<em>ProgId</em>&quot;, &quot;<em>computername</em>&quot;)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47763-117">进程内</span><span class="sxs-lookup"><span data-stu-id="47763-117">In-process</span></span></p></td>
<td><p><span data-ttu-id="47763-118">设置<em>对象</em> = 的<em>空间</em>。CreateObject (&quot;<em>ProgId</em>&quot;, &quot; &quot;)</span><span class="sxs-lookup"><span data-stu-id="47763-118">Set<em>object</em> = <em>DataSpace</em>.CreateObject(&quot;<em>ProgId</em>&quot;, &quot; &quot;)</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="parameters"></a><span data-ttu-id="47763-119">参数</span><span class="sxs-lookup"><span data-stu-id="47763-119">Parameters</span></span>

|<span data-ttu-id="47763-120">参数</span><span class="sxs-lookup"><span data-stu-id="47763-120">Parameter</span></span>|<span data-ttu-id="47763-121">描述</span><span class="sxs-lookup"><span data-stu-id="47763-121">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="47763-122">*Object*</span><span class="sxs-lookup"><span data-stu-id="47763-122">*Object*</span></span> |<span data-ttu-id="47763-123">一个对象变量，其值为 *ProgID* 中指定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="47763-123">An object variable that evaluates to an object that is the type specified in *ProgID*.</span></span>|
|<span data-ttu-id="47763-124">*DataSpace*</span><span class="sxs-lookup"><span data-stu-id="47763-124">*DataSpace*</span></span> |<span data-ttu-id="47763-125">对象变量，代表用于创建新对象实例的 [RDS.DataSpace](dataspace-object-rds.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="47763-125">An object variable that represents an [RDS.DataSpace](dataspace-object-rds.md) object used to create an instance of the new object.</span></span>|
|<span data-ttu-id="47763-126">*ProgID*</span><span class="sxs-lookup"><span data-stu-id="47763-126">*ProgID*</span></span> |<span data-ttu-id="47763-127">一个包含程序标识符的 **String** 值，指定用于实现应用程序的业务规则的服务器端业务对象。</span><span class="sxs-lookup"><span data-stu-id="47763-127">A **String** value that contains the programmatic identifier specifying a server-side business object that implements your application's business rules.</span></span>|
|<span data-ttu-id="47763-128">*awebsrvr* 或 *computername*</span><span class="sxs-lookup"><span data-stu-id="47763-128">*awebsrvr* or *computername*</span></span> |<span data-ttu-id="47763-129">一个**String**值, 它代表标识 Internet 信息服务 (IIS) web 服务器 (在其中创建服务器业务对象实例) 的 URL。</span><span class="sxs-lookup"><span data-stu-id="47763-129">A **String** value that represents a URL identifying the Internet Information Services (IIS) web server where an instance of the server business object is created.</span></span>|

## <a name="remarks"></a><span data-ttu-id="47763-130">注解</span><span class="sxs-lookup"><span data-stu-id="47763-130">Remarks</span></span>

<span data-ttu-id="47763-131">*HTTP 协议*是标准 web 协议;*HTTPS*是安全的 web 协议。</span><span class="sxs-lookup"><span data-stu-id="47763-131">The *HTTP protocol* is the standard web protocol; *HTTPS* is a secure web protocol.</span></span> <span data-ttu-id="47763-132">在不使用 HTTP 运行局域网时使用 *DCOM 协议*。</span><span class="sxs-lookup"><span data-stu-id="47763-132">Use the *DCOM protocol* when running a local-area network without HTTP.</span></span> <span data-ttu-id="47763-133">*进程内*协议是本地动态链接库 (DLL)；它不使用网络。</span><span class="sxs-lookup"><span data-stu-id="47763-133">The *in-process* protocol is a local dynamic-link library (DLL); it does not use a network.</span></span>

