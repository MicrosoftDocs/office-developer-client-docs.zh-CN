---
title: CreateObject 方法 (RDS)
TOCTitle: CreateObject method (RDS)
ms:assetid: 130debe5-31cf-4ab0-5f78-9adaec7d7126
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248905(v=office.15)
ms:contentKeyID: 48543360
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d08b596afb24fff430c6c662a557da1880addefa
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921178"
---
# <a name="createobject-method-rds"></a><span data-ttu-id="68a69-102">CreateObject 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="68a69-102">CreateObject method (RDS)</span></span>


<span data-ttu-id="68a69-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="68a69-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="68a69-p101">用于创建目标业务对象的代理，并返回指向该代理的指针。代理打包数据并将其封送到服务器端存根，用于与业务对象进行通信，以便通过 Internet 发送请求和数据。对于进程内组件对象，不使用代理，而仅提供指向对象的指针。</span><span class="sxs-lookup"><span data-stu-id="68a69-p101">Creates the proxy for the target business object and returns a pointer to it. The proxy packages and marshals data to the server-side stub for communications with the business object to send requests and data over the Internet. For in-process component objects, no proxies are used, just a pointer to the object is provided.</span></span>

## <a name="syntax"></a><span data-ttu-id="68a69-107">语法</span><span class="sxs-lookup"><span data-stu-id="68a69-107">Syntax</span></span>

<span data-ttu-id="68a69-108">远程数据服务支持以下协议：HTTP、HTTPS（基于安全套接字层的 HTTP）、DCOM 和进程内。</span><span class="sxs-lookup"><span data-stu-id="68a69-108">Remote Data Service supports the following protocols: HTTP, HTTPS (HTTP over Secure Socket Layer), DCOM, and in-process.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="68a69-109">协议</span><span class="sxs-lookup"><span data-stu-id="68a69-109">Protocol</span></span></p></th>
<th><p><span data-ttu-id="68a69-110">语法</span><span class="sxs-lookup"><span data-stu-id="68a69-110">Syntax</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68a69-111">HTTP</span><span class="sxs-lookup"><span data-stu-id="68a69-111">HTTP</span></span></p></td>
<td><p><span data-ttu-id="68a69-112">将<em>对象</em>设置 = <em>DataSpace</em>。CreateObject (&quot;<em>ProgId</em>&quot;， &quot; <em>https://awebsrvr</em> &quot;)</span><span class="sxs-lookup"><span data-stu-id="68a69-112">Set<em>object</em> = <em>DataSpace</em>.CreateObject(&quot;<em>ProgId</em>&quot;, &quot;<em>https://awebsrvr</em>&quot;)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68a69-113">HTTPS</span><span class="sxs-lookup"><span data-stu-id="68a69-113">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="68a69-114">将<em>对象</em>设置 = <em>DataSpace</em>。CreateObject (&quot;<em>ProgId</em>&quot;， &quot; <em>https://awebsrvr</em> &quot;)</span><span class="sxs-lookup"><span data-stu-id="68a69-114">Set<em>object</em> = <em>DataSpace</em>.CreateObject(&quot;<em>ProgId</em>&quot;, &quot;<em>https://awebsrvr</em>&quot;)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68a69-115">DCOM</span><span class="sxs-lookup"><span data-stu-id="68a69-115">DCOM</span></span></p></td>
<td><p><span data-ttu-id="68a69-116">将<em>对象</em>设置 = <em>DataSpace</em>。CreateObject (&quot;<em>ProgId</em>&quot;， &quot; <em>computername</em>&quot;)</span><span class="sxs-lookup"><span data-stu-id="68a69-116">Set<em>object</em> = <em>DataSpace</em>.CreateObject(&quot;<em>ProgId</em>&quot;, &quot;<em>computername</em>&quot;)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68a69-117">In-process</span><span class="sxs-lookup"><span data-stu-id="68a69-117">In-process</span></span></p></td>
<td><p><span data-ttu-id="68a69-118">将<em>对象</em>设置 = <em>DataSpace</em>。CreateObject (&quot;<em>ProgId</em>&quot;， &quot; &quot;)</span><span class="sxs-lookup"><span data-stu-id="68a69-118">Set<em>object</em> = <em>DataSpace</em>.CreateObject(&quot;<em>ProgId</em>&quot;, &quot; &quot;)</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="parameters"></a><span data-ttu-id="68a69-119">参数</span><span class="sxs-lookup"><span data-stu-id="68a69-119">Parameters</span></span>

  - <span data-ttu-id="68a69-120">*Object*</span><span class="sxs-lookup"><span data-stu-id="68a69-120">*Object*</span></span>

  - <span data-ttu-id="68a69-121">一个对象变量，其值为 *ProgID* 中指定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="68a69-121">An object variable that evaluates to an object that is the type specified in *ProgID*.</span></span>

  - <span data-ttu-id="68a69-122">*DataSpace*</span><span class="sxs-lookup"><span data-stu-id="68a69-122">*DataSpace*</span></span>

  - <span data-ttu-id="68a69-123">对象变量，代表用于创建新对象实例的 [RDS.DataSpace](dataspace-object-rds.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="68a69-123">An object variable that represents an [RDS.DataSpace](dataspace-object-rds.md) object used to create an instance of the new object.</span></span>

  - <span data-ttu-id="68a69-124">*ProgID*</span><span class="sxs-lookup"><span data-stu-id="68a69-124">*ProgID*</span></span>

  - <span data-ttu-id="68a69-125">一个包含程序标识符的 **String** 值，指定用于实现应用程序的业务规则的服务器端业务对象。</span><span class="sxs-lookup"><span data-stu-id="68a69-125">A **String** value that contains the programmatic identifier specifying a server-side business object that implements your application's business rules.</span></span>

  - <span data-ttu-id="68a69-126">*awebsrvr*或*computername*</span><span class="sxs-lookup"><span data-stu-id="68a69-126">*awebsrvr* or *computername*</span></span>

  - <span data-ttu-id="68a69-127">一个**字符串**值，代表标识在其中创建服务器业务对象的实例的 Internet 信息服务 (IIS) web 服务器的 URL。</span><span class="sxs-lookup"><span data-stu-id="68a69-127">A **String** value that represents a URL identifying the Internet Information Services (IIS) web server where an instance of the server business object is created.</span></span>

## <a name="remarks"></a><span data-ttu-id="68a69-128">说明</span><span class="sxs-lookup"><span data-stu-id="68a69-128">Remarks</span></span>

<span data-ttu-id="68a69-129">*HTTP 协议*是标准的 web 协议;*HTTPS*是安全的 web 协议。</span><span class="sxs-lookup"><span data-stu-id="68a69-129">The *HTTP protocol* is the standard web protocol; *HTTPS* is a secure web protocol.</span></span> <span data-ttu-id="68a69-130">运行没有 HTTP 的本地网络时，请使用*DCOM 协议*。</span><span class="sxs-lookup"><span data-stu-id="68a69-130">Use the *DCOM protocol* when running a local-area network without HTTP.</span></span> <span data-ttu-id="68a69-131">*进程内*协议是本地的动态链接库 (DLL);它不使用网络。</span><span class="sxs-lookup"><span data-stu-id="68a69-131">The *in-process* protocol is a local dynamic-link library (DLL); it does not use a network.</span></span>

