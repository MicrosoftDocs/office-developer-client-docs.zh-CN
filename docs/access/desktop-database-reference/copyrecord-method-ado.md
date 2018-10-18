---
title: CopyRecord 方法 (ADO)
TOCTitle: CopyRecord Method (ADO)
ms:assetid: 724e4358-f216-8e47-5bab-c72770ece5a4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249459(v=office.15)
ms:contentKeyID: 48545605
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 73940108f96cf46cb15d646936039c0329373899
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606904"
---
# <a name="copyrecord-method-ado"></a><span data-ttu-id="a2802-102">CopyRecord 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="a2802-102">CopyRecord Method (ADO)</span></span>


<span data-ttu-id="a2802-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a2802-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a2802-104">用于将由 **Record** 表示的实体复制到其他位置。</span><span class="sxs-lookup"><span data-stu-id="a2802-104">Copies a entity represented by a **Record** to another location.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2802-105">语法</span><span class="sxs-lookup"><span data-stu-id="a2802-105">Syntax</span></span>

<span data-ttu-id="a2802-106">*记录*。CopyRecord （*源*、 *Destination*、*用户名*、*密码*、*选项*、*异步*）</span><span class="sxs-lookup"><span data-stu-id="a2802-106">*Record*.CopyRecord (*Source*, *Destination*, *UserName*, *Password*, *Options*, *Async*)</span></span>

## <a name="parameters"></a><span data-ttu-id="a2802-107">参数</span><span class="sxs-lookup"><span data-stu-id="a2802-107">Parameters</span></span>

  - <span data-ttu-id="a2802-108">*Source*</span><span class="sxs-lookup"><span data-stu-id="a2802-108">*Source*</span></span>

  - <span data-ttu-id="a2802-109">可选。</span><span class="sxs-lookup"><span data-stu-id="a2802-109">Optional.</span></span> <span data-ttu-id="a2802-110">**字符串型** 值，包含用于指定要复制的实体（如文件或目录）的 URL。</span><span class="sxs-lookup"><span data-stu-id="a2802-110">A **String** value that contains a URL specifying the entity to be copied (for example, a file or directory).</span></span> <span data-ttu-id="a2802-111">如果*源*被省略，或指定为空字符串，将复制的文件或当前[Record](record-object-ado.md)所表示的目录。</span><span class="sxs-lookup"><span data-stu-id="a2802-111">If *Source* is omitted or specifies an empty string, the file or directory represented by the current [Record](record-object-ado.md) will be copied.</span></span>

  - <span data-ttu-id="a2802-112">*Destination*</span><span class="sxs-lookup"><span data-stu-id="a2802-112">*Destination*</span></span>

  - <span data-ttu-id="a2802-113">可选。</span><span class="sxs-lookup"><span data-stu-id="a2802-113">Optional.</span></span> <span data-ttu-id="a2802-114">一个**字符串**值，包含指定将在其中复制*源*的位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="a2802-114">A **String** value that contains a URL specifying the location where *Source* will be copied.</span></span>

  - <span data-ttu-id="a2802-115">*UserName*</span><span class="sxs-lookup"><span data-stu-id="a2802-115">*UserName*</span></span>

  - <span data-ttu-id="a2802-p103">可选。包含用户 ID 的**字符串型**值，如果需要，将授予访问 *Destination* 的权限。</span><span class="sxs-lookup"><span data-stu-id="a2802-p103">Optional. A **String** value that contains the user ID that, if needed, authorizes access to *Destination*.</span></span>

  - <span data-ttu-id="a2802-118">*Password*</span><span class="sxs-lookup"><span data-stu-id="a2802-118">*Password*</span></span>

  - <span data-ttu-id="a2802-p104">可选。包含密码的**字符串型**值，如果需要，将验证 *UserName*。</span><span class="sxs-lookup"><span data-stu-id="a2802-p104">Optional. A **String** value that contains the password that, if needed, verifies *UserName*.</span></span>

  - <span data-ttu-id="a2802-121">*Options*</span><span class="sxs-lookup"><span data-stu-id="a2802-121">*Options*</span></span>

  - <span data-ttu-id="a2802-p105">可选。[CopyRecordOptionsEnum](copyrecordoptionsenum.md) 值，其默认值为 **adCopyUnspecified** 。指定该方法的行为。</span><span class="sxs-lookup"><span data-stu-id="a2802-p105">Optional. A [CopyRecordOptionsEnum](copyrecordoptionsenum.md) value that has a default value of **adCopyUnspecified**. Specifies the behavior of this method.</span></span>

  - <span data-ttu-id="a2802-125">*Async*</span><span class="sxs-lookup"><span data-stu-id="a2802-125">*Async*</span></span>

  - <span data-ttu-id="a2802-p106">可选。一个 **Boolean** 值，为 **True** 时，指定此操作应为异步。</span><span class="sxs-lookup"><span data-stu-id="a2802-p106">Optional. A **Boolean** value that, when **True**, specifies that this operation should be asynchronous.</span></span>

<span data-ttu-id="a2802-128"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="a2802-128"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="a2802-129">返回值</span><span class="sxs-lookup"><span data-stu-id="a2802-129">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="a2802-130">返回值</span><span class="sxs-lookup"><span data-stu-id="a2802-130">Return value</span></span>
>>>>>>> <span data-ttu-id="a2802-131">master</span><span class="sxs-lookup"><span data-stu-id="a2802-131">master</span></span>

<span data-ttu-id="a2802-p107">**字符串型**值，通常返回 *Destination* 的值。不过，返回的确切值与提供程序有关。</span><span class="sxs-lookup"><span data-stu-id="a2802-p107">A **String** value that typically returns the value of *Destination*. However, the exact value returned is provider-dependent.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2802-134">说明</span><span class="sxs-lookup"><span data-stu-id="a2802-134">Remarks</span></span>

<span data-ttu-id="a2802-135">*源*和*目标*值不能相同;否则，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="a2802-135">The values of *Source* and *Destination* must not be identical; otherwise, a run-time error occurs.</span></span> <span data-ttu-id="a2802-136">服务器、路径和资源名中必须至少有一个不同。</span><span class="sxs-lookup"><span data-stu-id="a2802-136">At least one of the server, path, or resource names must differ.</span></span>

<span data-ttu-id="a2802-p109">除非指定 **adCopyNonRecursive**，否则 *Source* 的所有子级（如子目录）以递归方式进行复制。在递归操作中，*Destination* 不能是 *Source* 的子目录；否则，操作将无法完成。</span><span class="sxs-lookup"><span data-stu-id="a2802-p109">All children (for example, subdirectories) of *Source* are copied recursively, unless **adCopyNonRecursive** is specified. In a recursive operation, *Destination* must not be a subdirectory of *Source*; otherwise, the operation will not complete.</span></span>

<span data-ttu-id="a2802-139">如果*Destination*标识现有实体 （如文件或目录），除非指定了**adCopyOverWrite** ，此方法将失败。</span><span class="sxs-lookup"><span data-stu-id="a2802-139">This method fails if *Destination* identifies an existing entity (for example, a file or directory), unless **adCopyOverWrite** is specified.</span></span>


> [!IMPORTANT]
> <P><span data-ttu-id="a2802-140">[!重要信息] 应谨慎使用 <STRONG>adCopyOverWrite</STRONG> 选项。</span><span class="sxs-lookup"><span data-stu-id="a2802-140">Use the <STRONG>adCopyOverWrite</STRONG> option judiciously.</span></span> <span data-ttu-id="a2802-141">例如，将文件复制到目录时指定此选项将<EM>删除</EM>目录和替换该文件。</span><span class="sxs-lookup"><span data-stu-id="a2802-141">For example, specifying this option when copying a file to a directory will <EM>delete</EM> the directory and replace it with the file.</span></span></P>




> [!NOTE]
<span data-ttu-id="a2802-142"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="a2802-142"><<<<<<< HEAD</span></span>
> <P><span data-ttu-id="a2802-p111">[!注释] 使用 HTTP 架构的 URL 将自动调用 <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>。有关详细信息，请参阅<A href="absolute-and-relative-urls.md">绝对 URL 和相对 URL</A>。</span><span class="sxs-lookup"><span data-stu-id="a2802-p111">URLs using the http scheme will automatically invoke the <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>. For more information, see <A href="absolute-and-relative-urls.md">Absolute and Relative URLs</A>.</span></span></P>
=======
> <span data-ttu-id="a2802-145">[!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="a2802-145">URLs using the http scheme will automatically invoke the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md).</span></span> <span data-ttu-id="a2802-146">有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="a2802-146">For more information, see [Absolute and relative URLs](absolute-and-relative-urls.md).</span></span>
>>>>>>> <span data-ttu-id="a2802-147">master</span><span class="sxs-lookup"><span data-stu-id="a2802-147">master</span></span>


