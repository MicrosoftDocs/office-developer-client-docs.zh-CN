---
title: CopyRecord 方法 (ADO)
TOCTitle: CopyRecord method (ADO)
ms:assetid: 724e4358-f216-8e47-5bab-c72770ece5a4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249459(v=office.15)
ms:contentKeyID: 48545605
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c5aac745bacf0662f6cd389bfefde7182a9676d3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295525"
---
# <a name="copyrecord-method-ado"></a><span data-ttu-id="c5801-102">CopyRecord 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c5801-102">CopyRecord method (ADO)</span></span>

<span data-ttu-id="c5801-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c5801-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c5801-104">用于将由 **Record** 表示的实体复制到其他位置。</span><span class="sxs-lookup"><span data-stu-id="c5801-104">Copies a entity represented by a **Record** to another location.</span></span>

## <a name="syntax"></a><span data-ttu-id="c5801-105">语法</span><span class="sxs-lookup"><span data-stu-id="c5801-105">Syntax</span></span>

<span data-ttu-id="c5801-106">*记录*。CopyRecord (*源*、*目标*、*用户名*、*密码*、*选项*、*异步*)</span><span class="sxs-lookup"><span data-stu-id="c5801-106">*Record*.CopyRecord (*Source*, *Destination*, *UserName*, *Password*, *Options*, *Async*)</span></span>

## <a name="parameters"></a><span data-ttu-id="c5801-107">参数</span><span class="sxs-lookup"><span data-stu-id="c5801-107">Parameters</span></span>

|<span data-ttu-id="c5801-108">参数</span><span class="sxs-lookup"><span data-stu-id="c5801-108">Parameter</span></span>|<span data-ttu-id="c5801-109">描述</span><span class="sxs-lookup"><span data-stu-id="c5801-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="c5801-110">*Source*</span><span class="sxs-lookup"><span data-stu-id="c5801-110">*Source*</span></span> |<span data-ttu-id="c5801-p101">可选。**字符串型**值，包含用于指定要复制的实体（如文件或目录）的 URL。如果忽略 *Source* 或者指定一个空字符串，将复制由当前 [Record](record-object-ado.md) 表示的文件或目录。</span><span class="sxs-lookup"><span data-stu-id="c5801-p101">Optional. A **String** value that contains a URL specifying the entity to be copied (for example, a file or directory). If *Source* is omitted or specifies an empty string, the file or directory represented by the current [Record](record-object-ado.md) will be copied.</span></span>|
|<span data-ttu-id="c5801-114">*目标*</span><span class="sxs-lookup"><span data-stu-id="c5801-114">*Destination*</span></span> |<span data-ttu-id="c5801-115">可选。</span><span class="sxs-lookup"><span data-stu-id="c5801-115">Optional.</span></span> <span data-ttu-id="c5801-116">**字符串型**值，包含用于指定 *Source* 将复制到的位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="c5801-116">A **String** value that contains a URL specifying the location where *Source* will be copied.</span></span>|
|<span data-ttu-id="c5801-117">*UserName*</span><span class="sxs-lookup"><span data-stu-id="c5801-117">*UserName*</span></span> |<span data-ttu-id="c5801-118">可选。</span><span class="sxs-lookup"><span data-stu-id="c5801-118">Optional.</span></span> <span data-ttu-id="c5801-119">包含用户 ID 的**字符串型**值，如果需要，将授予访问 *Destination* 的权限。</span><span class="sxs-lookup"><span data-stu-id="c5801-119">A **String** value that contains the user ID that, if needed, authorizes access to *Destination*.</span></span>|
|<span data-ttu-id="c5801-120">*Password*</span><span class="sxs-lookup"><span data-stu-id="c5801-120">*Password*</span></span> |<span data-ttu-id="c5801-121">可选。</span><span class="sxs-lookup"><span data-stu-id="c5801-121">Optional.</span></span> <span data-ttu-id="c5801-122">包含密码的**字符串型**值，如果需要，将验证 *UserName*。</span><span class="sxs-lookup"><span data-stu-id="c5801-122">A **String** value that contains the password that, if needed, verifies *UserName*.</span></span>|
|<span data-ttu-id="c5801-123">*Options*</span><span class="sxs-lookup"><span data-stu-id="c5801-123">*Options*</span></span> |<span data-ttu-id="c5801-p105">可选。[CopyRecordOptionsEnum](copyrecordoptionsenum.md) 值，其默认值为 **adCopyUnspecified** 。指定该方法的行为。</span><span class="sxs-lookup"><span data-stu-id="c5801-p105">Optional. A [CopyRecordOptionsEnum](copyrecordoptionsenum.md) value that has a default value of **adCopyUnspecified**. Specifies the behavior of this method.</span></span>|
|<span data-ttu-id="c5801-127">*Async*</span><span class="sxs-lookup"><span data-stu-id="c5801-127">*Async*</span></span> |<span data-ttu-id="c5801-p106">可选。一个 **Boolean** 值，为 **True** 时，指定此操作应为异步。</span><span class="sxs-lookup"><span data-stu-id="c5801-p106">Optional. A **Boolean** value that, when **True**, specifies that this operation should be asynchronous.</span></span>|

## <a name="return-value"></a><span data-ttu-id="c5801-130">返回值</span><span class="sxs-lookup"><span data-stu-id="c5801-130">Return value</span></span>

<span data-ttu-id="c5801-131">**字符串型**值，通常返回 *Destination* 的值。</span><span class="sxs-lookup"><span data-stu-id="c5801-131">A **String** value that typically returns the value of *Destination*.</span></span> <span data-ttu-id="c5801-132">不过，返回的确切值与提供程序有关。</span><span class="sxs-lookup"><span data-stu-id="c5801-132">However, the exact value returned is provider-dependent.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5801-133">注解</span><span class="sxs-lookup"><span data-stu-id="c5801-133">Remarks</span></span>

<span data-ttu-id="c5801-p108">*Source* 和 *Destination* 的值不能相同；否则，将发生运行时错误。服务器、路径和资源名中必须至少有一个不同。</span><span class="sxs-lookup"><span data-stu-id="c5801-p108">The values of *Source* and *Destination* must not be identical; otherwise, a run-time error occurs. At least one of the server, path, or resource names must differ.</span></span>

<span data-ttu-id="c5801-p109">除非指定 **adCopyNonRecursive**，否则 *Source* 的所有子级（如子目录）以递归方式进行复制。在递归操作中，*Destination* 不能是 *Source* 的子目录；否则，操作将无法完成。</span><span class="sxs-lookup"><span data-stu-id="c5801-p109">All children (for example, subdirectories) of *Source* are copied recursively, unless **adCopyNonRecursive** is specified. In a recursive operation, *Destination* must not be a subdirectory of *Source*; otherwise, the operation will not complete.</span></span>

<span data-ttu-id="c5801-138">如果 *Destination* 标识现有的实体（如文件或目录），该方法将失败，除非指定了 **adCopyOverWrite**。</span><span class="sxs-lookup"><span data-stu-id="c5801-138">This method fails if *Destination* identifies an existing entity (for example, a file or directory), unless **adCopyOverWrite** is specified.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5801-p110">应谨慎使用 **adCopyOverWrite** 选项。例如，在将文件复制到目录时指定此选项将*删除*该目录并替换为复制的文件。</span><span class="sxs-lookup"><span data-stu-id="c5801-p110">Use the **adCopyOverWrite** option judiciously. For example, specifying this option when copying a file to a directory will *delete* the directory and replace it with the file.</span></span>


> [!NOTE]
> <span data-ttu-id="c5801-141">[!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="c5801-141">URLs using the http scheme will automatically invoke the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md).</span></span> <span data-ttu-id="c5801-142">有关详细信息, 请参阅[绝对和相对 url](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="c5801-142">For more information, see [Absolute and relative URLs](absolute-and-relative-urls.md).</span></span>


