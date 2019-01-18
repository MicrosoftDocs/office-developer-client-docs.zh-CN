---
title: DeleteRecord 方法 (ADO)
TOCTitle: DeleteRecord method (ADO)
ms:assetid: ba71187f-e580-bba8-f41b-bedfa0bc2b04
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249895(v=office.15)
ms:contentKeyID: 48547370
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8d6ecd408bc2141ef9ff4bec8f6469a70e09bbe1
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704516"
---
# <a name="deleterecord-method-ado"></a><span data-ttu-id="0d917-102">DeleteRecord 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="0d917-102">DeleteRecord method (ADO)</span></span>

<span data-ttu-id="0d917-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0d917-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0d917-104">用于删除由 [Record](record-object-ado.md) 表示的实体。</span><span class="sxs-lookup"><span data-stu-id="0d917-104">Deletes a the entity represented by a [Record](record-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="0d917-105">语法</span><span class="sxs-lookup"><span data-stu-id="0d917-105">Syntax</span></span>

<span data-ttu-id="0d917-106">*记录*。 \**DeleteRecord \*\*\* 源*，*异步*</span><span class="sxs-lookup"><span data-stu-id="0d917-106">*Record*.\**DeleteRecord\*\*\*Source*, *Async*</span></span>

## <a name="parameters"></a><span data-ttu-id="0d917-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="0d917-107">Parameters</span></span>

|<span data-ttu-id="0d917-108">参数</span><span class="sxs-lookup"><span data-stu-id="0d917-108">Parameter</span></span>|<span data-ttu-id="0d917-109">说明</span><span class="sxs-lookup"><span data-stu-id="0d917-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="0d917-110">*Source*</span><span class="sxs-lookup"><span data-stu-id="0d917-110">*Source*</span></span> |<span data-ttu-id="0d917-p101">可选。**字符串型**值，包含用于标识要删除的实体（如文件或目录）的 URL。如果忽略 *Source* 或者指定一个空字符串，将删除由当前 [Record](record-object-ado.md) 表示的实体。如果该 Record 是一个集合记录（**adCollectionRecord** 的 [RecordType](recordtype-property-ado.md)，例如目录），还将删除所有子级（如子目录）。</span><span class="sxs-lookup"><span data-stu-id="0d917-p101">Optional. A **String** value that contains a URL identifying the entity (for example, the file or directory) to be deleted. If *Source* is omitted or specifies an empty string, the entity represented by the current [Record](record-object-ado.md) is deleted. If the Record is a collection record ([RecordType](recordtype-property-ado.md) of **adCollectionRecord**, such as a directory) all children (for example, subdirectories) will also be deleted.</span></span>|
|<span data-ttu-id="0d917-115">*Async*</span><span class="sxs-lookup"><span data-stu-id="0d917-115">*Async*</span></span> |<span data-ttu-id="0d917-p102">可选。一个 **Boolean** 值，为 **True** 时，指定删除操作为异步。</span><span class="sxs-lookup"><span data-stu-id="0d917-p102">Optional. A **Boolean** value that, when **True**, specifies that the delete operation is asynchronous.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0d917-118">说明</span><span class="sxs-lookup"><span data-stu-id="0d917-118">Remarks</span></span>

<span data-ttu-id="0d917-p103">该方法完成之后，由此 **Record** 表示的对象上的操作可能会失败。由于此 **Record** 的行为将取决于提供程序何时用数据源来更新它，因此 **Record** 的行为变得无法预测，调用 **DeleteRecord** 之后，应关闭此 **Record** 。</span><span class="sxs-lookup"><span data-stu-id="0d917-p103">Operations on the object represented by this **Record** may fail after this method completes. After calling **DeleteRecord**, the **Record** should be closed because the behavior of the **Record** may become unpredictable depending upon when the provider updates the **Record** with the data source.</span></span>

<span data-ttu-id="0d917-121">如果此 **Record** 是从 [Recordset](recordset-object-ado.md) 获取的，则该操作的结果将不会立即反映到 **Recordset** 中。</span><span class="sxs-lookup"><span data-stu-id="0d917-121">If this **Record** was obtained from a [Recordset](recordset-object-ado.md), then the results of this operation will not be reflected immediately in the **Recordset**.</span></span> <span data-ttu-id="0d917-122">关闭并重新打开它，或通过执行的**Recordset**的[Requery](requery-method-ado.md)，或[更新](update-method-ado.md)和[Resync](resync-method-ado.md)方法刷新**Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="0d917-122">Refresh the **Recordset** by closing and re-opening it, or by executing the **Recordset** [Requery](requery-method-ado.md), or [Update](update-method-ado.md) and [Resync](resync-method-ado.md) methods.</span></span>

> [!NOTE]
> <span data-ttu-id="0d917-123">[!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="0d917-123">URLs using the http scheme will automatically invoke the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md).</span></span> <span data-ttu-id="0d917-124">有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="0d917-124">For more information, see [Absolute and relative URLs](absolute-and-relative-urls.md).</span></span>


