---
title: MoveRecord 方法 (ADO)
TOCTitle: MoveRecord method (ADO)
ms:assetid: efc341a2-0e08-a838-5925-8d4c46377e48
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250217(v=office.15)
ms:contentKeyID: 48548588
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c9937f0ab32c5dba0e4435fdc0ba7e111f5651dc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288677"
---
# <a name="moverecord-method-ado"></a><span data-ttu-id="6857c-102">MoveRecord 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="6857c-102">MoveRecord method (ADO)</span></span>

<span data-ttu-id="6857c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6857c-103">**Applies to**: Access 2013, Office 2013</span></span>
 
<span data-ttu-id="6857c-104">用于将由 [Record](record-object-ado.md) 表示的实体移动到其他位置。</span><span class="sxs-lookup"><span data-stu-id="6857c-104">Moves the entity represent by a [Record](record-object-ado.md) to another location.</span></span>

## <a name="syntax"></a><span data-ttu-id="6857c-105">语法</span><span class="sxs-lookup"><span data-stu-id="6857c-105">Syntax</span></span>

<span data-ttu-id="6857c-106">*记录*。MoveRecord (*源*、*目标*、*用户名*、*密码*、*选项*、*异步*)</span><span class="sxs-lookup"><span data-stu-id="6857c-106">*Record*.MoveRecord (*Source*, *Destination*, *UserName*, *Password*, *Options*, *Async*)</span></span>

## <a name="parameters"></a><span data-ttu-id="6857c-107">参数</span><span class="sxs-lookup"><span data-stu-id="6857c-107">Parameters</span></span>

|<span data-ttu-id="6857c-108">参数</span><span class="sxs-lookup"><span data-stu-id="6857c-108">Parameter</span></span>|<span data-ttu-id="6857c-109">描述</span><span class="sxs-lookup"><span data-stu-id="6857c-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="6857c-110">*Source*</span><span class="sxs-lookup"><span data-stu-id="6857c-110">*Source*</span></span> |<span data-ttu-id="6857c-p101">可选。**字符串型**值，包含标识要移动的 **Record** 的 URL。如果忽略 *Source* 或者指定一个空字符串，将删除由该 **Record** 表示的对象。例如，如果 **Record** 代表文件，则将文件的内容移动到由 *Destination* 指定的位置。</span><span class="sxs-lookup"><span data-stu-id="6857c-p101">Optional. A **String** value that contains a URL identifying the **Record** to be moved. If *Source* is omitted or specifies an empty string, the object represented by this **Record** is moved. For example, if the **Record** represents a file, the contents of the file are moved to the location specified by *Destination*.</span></span>|
|<span data-ttu-id="6857c-115">*目标*</span><span class="sxs-lookup"><span data-stu-id="6857c-115">*Destination*</span></span> |<span data-ttu-id="6857c-116">可选。</span><span class="sxs-lookup"><span data-stu-id="6857c-116">Optional.</span></span> <span data-ttu-id="6857c-117">**字符串型**值，包含用于指定 *Source* 将移动到的位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="6857c-117">A **String** value that contains a URL specifying the location where *Source* will be moved.</span></span>|
|<span data-ttu-id="6857c-118">*UserName*</span><span class="sxs-lookup"><span data-stu-id="6857c-118">*UserName*</span></span> |<span data-ttu-id="6857c-119">可选。</span><span class="sxs-lookup"><span data-stu-id="6857c-119">Optional.</span></span> <span data-ttu-id="6857c-120">包含用户 ID 的**字符串型**值，如果需要，将授予访问 *Destination* 的权限。</span><span class="sxs-lookup"><span data-stu-id="6857c-120">A **String** value that contains the user ID that, if needed, authorizes access to *Destination*.</span></span>|
|<span data-ttu-id="6857c-121">*Password*</span><span class="sxs-lookup"><span data-stu-id="6857c-121">*Password*</span></span> |<span data-ttu-id="6857c-122">可选。</span><span class="sxs-lookup"><span data-stu-id="6857c-122">Optional.</span></span> <span data-ttu-id="6857c-123">包含密码的**字符串型**值，如果需要，将通过该密码验证 *UserName*。</span><span class="sxs-lookup"><span data-stu-id="6857c-123">A **String** that contains the password that, if needed, verifies *UserName*.</span></span>|
|<span data-ttu-id="6857c-124">*Options*</span><span class="sxs-lookup"><span data-stu-id="6857c-124">*Options*</span></span> |<span data-ttu-id="6857c-p105">可选。[MoveRecordOptionsEnum](moverecordoptionsenum.md) 值，其默认值为 **adMoveUnspecified** 。指定该方法的行为。</span><span class="sxs-lookup"><span data-stu-id="6857c-p105">Optional. A [MoveRecordOptionsEnum](moverecordoptionsenum.md) value whose default value is **adMoveUnspecified**. Specifies the behavior of this method.</span></span>|
|<span data-ttu-id="6857c-128">*Async*</span><span class="sxs-lookup"><span data-stu-id="6857c-128">*Async*</span></span> |<span data-ttu-id="6857c-129">可选。</span><span class="sxs-lookup"><span data-stu-id="6857c-129">Optional.</span></span> <span data-ttu-id="6857c-130">一个**布尔**值, 如果**为 True, 则**指定此操作应为异步操作。</span><span class="sxs-lookup"><span data-stu-id="6857c-130">A **Boolean** value that, when **True**, specifies this operation should be asynchronous.</span></span>|

## <a name="return-value"></a><span data-ttu-id="6857c-131">返回值</span><span class="sxs-lookup"><span data-stu-id="6857c-131">Return value</span></span>

<span data-ttu-id="6857c-132">**字符串型**值。</span><span class="sxs-lookup"><span data-stu-id="6857c-132">A **String** value.</span></span> <span data-ttu-id="6857c-133">通常返回 *Destination* 的值。</span><span class="sxs-lookup"><span data-stu-id="6857c-133">Typically, the value of *Destination* is returned.</span></span> <span data-ttu-id="6857c-134">但是，返回的确切值与提供程序有关。</span><span class="sxs-lookup"><span data-stu-id="6857c-134">However, the exact value returned is provider-dependent.</span></span>

## <a name="remarks"></a><span data-ttu-id="6857c-135">注解</span><span class="sxs-lookup"><span data-stu-id="6857c-135">Remarks</span></span>

<span data-ttu-id="6857c-p108">*Source* 和 *Destination* 的值不能相同；否则，将发生运行时错误。至少服务器、路径和资源名必须不同。</span><span class="sxs-lookup"><span data-stu-id="6857c-p108">The values of *Source* and *Destination* must not be identical; otherwise, a run-time error occurs. At least the server, path, and resource names must differ.</span></span>

<span data-ttu-id="6857c-p109">对于使用 Internet Publishing Provider 移动的文件，该方法更新被移动文件中的所有超文本链接，除非 *Options* 另有指定。如果 *Destination* 标识现有的对象（如文件或目录），该方法将失败，除非指定 **adMoveOverWrite**。</span><span class="sxs-lookup"><span data-stu-id="6857c-p109">For files moved using the Internet Publishing Provider, this method updates all hypertext links in files being moved unless otherwise specified by *Options*. This method fails if *Destination* identifies an existing object (for example, a file or directory), unless **adMoveOverWrite** is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="6857c-p110">[!注释] 应谨慎使用 **adMoveOverWrite** 选项。例如，在将文件移动到目录时指定此选项将删除该目录并替换为复制的文件。</span><span class="sxs-lookup"><span data-stu-id="6857c-p110">Use the **adMoveOverWrite** option judiciously. For example, specifying this option when moving a file to a directory will delete the directory and replace it with the file.</span></span>

<span data-ttu-id="6857c-p111">**Record** 对象的某些属性（如 [ParentURL](parenturl-property-ado.md) 属性）在该操作完成后不会更新。可以通过以下方法来刷新 **Record** 对象的属性：关闭 **Record** ，然后使用文件或目录移动到的位置的 URL 重新打开该记录。</span><span class="sxs-lookup"><span data-stu-id="6857c-p111">Certain attributes of the **Record** object, such as the [ParentURL](parenturl-property-ado.md) property, will not be updated after this operation completes. Refresh the **Record** object's properties by closing the **Record**, then re-opening it with the URL of the location where the file or directory was moved.</span></span>

<span data-ttu-id="6857c-p112">如果此 **Record** 是从 [Recordset](recordset-object-ado.md) 获取的，则移动的文件或目录的新位置将不会立即反映到 **Recordset** 中。您可以刷新 **Recordset** ，方法是关闭并重新打开它。</span><span class="sxs-lookup"><span data-stu-id="6857c-p112">If this **Record** was obtained from a [Recordset](recordset-object-ado.md), the new location of the moved file or directory will not be reflected immediately in the **Recordset**. Refresh the **Recordset** by closing and re-opening it.</span></span>

> [!NOTE]
> <span data-ttu-id="6857c-146">[!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="6857c-146">URLs using the http scheme will automatically invoke the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md).</span></span> <span data-ttu-id="6857c-147">有关详细信息, 请参阅[绝对和相对 url](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="6857c-147">For more information, see [Absolute and relative URLs](absolute-and-relative-urls.md).</span></span>


