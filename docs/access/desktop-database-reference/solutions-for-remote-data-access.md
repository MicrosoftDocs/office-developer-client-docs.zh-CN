---
title: 远程数据访问解决方案
TOCTitle: Solutions for Remote Data Access
ms:assetid: ae84c05a-cf9b-2b4c-4d7a-e6c9dcd120c1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249825(v=office.15)
ms:contentKeyID: 48547072
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9b64ed19c268874e0e52a87bc2e05aacb6083422
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711502"
---
# <a name="solutions-for-remote-data-access"></a><span data-ttu-id="46202-102">远程数据访问解决方案</span><span class="sxs-lookup"><span data-stu-id="46202-102">Solutions for Remote Data Access</span></span>

<span data-ttu-id="46202-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="46202-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="the-issue"></a><span data-ttu-id="46202-104">问题</span><span class="sxs-lookup"><span data-stu-id="46202-104">The issue</span></span>

<span data-ttu-id="46202-p101">应用程序可以通过 ADO 直接访问并修改数据源（有时称为双层系统）。例如，如果应用程序与包含数据的数据源连接，那么这就是双层系统中的直接连接。</span><span class="sxs-lookup"><span data-stu-id="46202-p101">ADO enables your application to directly gain access to and modify data sources (sometimes called a two-tier system). For example, if your connection is to the data source that contains your data, that is a direct connection in a two-tier system.</span></span>

<span data-ttu-id="46202-107">但是，您可能要通过如 Microsoft Internet 信息服务 (IIS) 中间间接访问数据源。</span><span class="sxs-lookup"><span data-stu-id="46202-107">However, you may want to access data sources indirectly through an intermediary such as Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="46202-108">这种安排有时称为三层系统。</span><span class="sxs-lookup"><span data-stu-id="46202-108">This arrangement is sometimes called a three-tier system.</span></span> <span data-ttu-id="46202-109">IIS 是一种客户端/服务器系统，为本地（或客户端）应用程序通过 Internet 或 Intranet 调用远程（或服务器）程序提供了有效的方式。</span><span class="sxs-lookup"><span data-stu-id="46202-109">IIS is a client/server system that provides an efficient way for a local, or client, application to invoke a remote, or server, program across the Internet or an intranet.</span></span> <span data-ttu-id="46202-110">服务器程序获取数据源的访问权，并可以选择对获得的数据进行处理。</span><span class="sxs-lookup"><span data-stu-id="46202-110">The server program gains access to the data source and optionally processes the acquired data.</span></span>

<span data-ttu-id="46202-111">例如，intranet 网页包含在 Microsoft Visual Basic Scripting Edition (VBScript) 中，将连接到 IIS 编写的应用程序。</span><span class="sxs-lookup"><span data-stu-id="46202-111">For example, your intranet webpage contains an application written in Microsoft Visual Basic Scripting Edition (VBScript), which connects to IIS.</span></span> <span data-ttu-id="46202-112">IIS 检索数据，并采用某种方式对数据进行处理，然后将处理过的信息返回给应用程序。</span><span class="sxs-lookup"><span data-stu-id="46202-112">IIS in turn connects to the actual data source, retrieves the data, processes it in some way, and then returns the processed information to your application.</span></span>

<span data-ttu-id="46202-p104">在本例中，应用程序始终都不与数据源直接连接，与数据源直接连接的是 IIS。且 IIS 通过 ADO 来访问数据。</span><span class="sxs-lookup"><span data-stu-id="46202-p104">In this example, your application never directly connected to the data source; IIS did. And IIS accessed the data by means of ADO.</span></span>

> [!NOTE]
> <span data-ttu-id="46202-115">不需要基于 Internet 或 intranet 上的客户端/服务器应用程序 (即，基于 web 的) — 它可以包含单独的局域网上编译的程序。</span><span class="sxs-lookup"><span data-stu-id="46202-115">The client/server application does not have to be based on the Internet or an intranet (that is, web-based)—it could consist solely of compiled programs on a local area network.</span></span> <span data-ttu-id="46202-116">但是，典型情况是基于 web 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="46202-116">However, the typical case is a web-based application.</span></span>

<span data-ttu-id="46202-117">由于某些可视控件（如网格、复选框或列表）可能使用返回的信息，因此可视控件必须能方便地使用返回的信息。</span><span class="sxs-lookup"><span data-stu-id="46202-117">Because some visual control, such as a grid, check box, or list, may use the returned information, the returned information must be easily used by a visual control.</span></span>

<span data-ttu-id="46202-p106">您需要一个简单而有效的应用程序编程接口，以支持三层系统，并像在双层系统中检索数据那样轻松地返回信息。远程数据服务 (RDS) 就是这样的接口。</span><span class="sxs-lookup"><span data-stu-id="46202-p106">You want a simple and efficient application-programming interface that supports three-tier systems, and returns information as easily as if it had been retrieved on a two-tier system. Remote Data Service (RDS) is this interface.</span></span>

## <a name="the-solution"></a><span data-ttu-id="46202-120">解决方案</span><span class="sxs-lookup"><span data-stu-id="46202-120">The solution</span></span>

<span data-ttu-id="46202-121">RDS 定义编程模型 — 活动需要访问和更新数据源的顺序 — 即可通过中间，如 Internet 信息服务 (IIS) 中的数据访问。</span><span class="sxs-lookup"><span data-stu-id="46202-121">RDS defines a programming model—the sequence of activities necessary to gain access to and update a data source — to gain access to data through an intermediary, such as Internet Information Services (IIS).</span></span> <span data-ttu-id="46202-122">编程模型中囊括了 RDS 的全部功能。</span><span class="sxs-lookup"><span data-stu-id="46202-122">The programming model summarizes the entire functionality of RDS.</span></span>

