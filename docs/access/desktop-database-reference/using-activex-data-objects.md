---
title: 使用 ActiveX 数据对象
TOCTitle: Use ActiveX Data Objects
description: Microsoft Access 提供了三种对象模型, 可用于创建、维护和管理 Access 数据库及其相关数据 (使用 Visual Basic)。
ms:assetid: 64055c45-7a27-2296-468a-015362898329
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194969(v=office.15)
ms:contentKeyID: 48545279
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm5285627
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 3b530db43a816e66b9fbef254984142aadf0b841
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32312738"
---
# <a name="use-activex-data-objects"></a><span data-ttu-id="ab2e1-103">使用 ActiveX 数据对象</span><span class="sxs-lookup"><span data-stu-id="ab2e1-103">Use ActiveX Data Objects</span></span>

<span data-ttu-id="ab2e1-104">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ab2e1-104">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ab2e1-105">Microsoft Access 提供了三种对象模型, 可用于创建、维护和管理 Access 数据库及其相关数据 (使用 Visual Basic)。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-105">Microsoft Access provides three object models to use in the creation, maintaining, and managing of your Access databases and their related data by using Visual Basic.</span></span>

## <a name="microsoft-activex-data-objects-ado"></a><span data-ttu-id="ab2e1-106">Microsoft ActiveX 数据对象 (ADO)</span><span class="sxs-lookup"><span data-stu-id="ab2e1-106">Microsoft ActiveX Data Objects (ADO)</span></span>

<span data-ttu-id="ab2e1-107">ADO 包含在给定数据源中创建、维护和删除记录所需的对象。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-107">ADO contains the objects needed to create, maintain, and delete records in a given datasource.</span></span>

## <a name="microsoft-ado-ext-for-ddl-and-security-adox"></a><span data-ttu-id="ab2e1-108">Microsoft ADO ext (针对 DDL 和安全性) (ADOX)</span><span class="sxs-lookup"><span data-stu-id="ab2e1-108">Microsoft ADO ext. for DDL and security (ADOX)</span></span>

<span data-ttu-id="ab2e1-109">除了管理安全性所需的对象之外, ADOX 还提供了创建新数据库及其包含的对象所需的数据定义语言 (DDL) 对象。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-109">ADOX provides the Data Definition Language (DDL) objects needed to create a new database and its contained objects in addition to the objects needed to manage security.</span></span>

### <a name="microsoft-jet-and-replication-objects-25-library-jro"></a><span data-ttu-id="ab2e1-110">Microsoft Jet 和 Replication 对象2.5 库 (JRO)</span><span class="sxs-lookup"><span data-stu-id="ab2e1-110">Microsoft Jet and Replication Objects 2.5 library (JRO)</span></span>

<span data-ttu-id="ab2e1-111">由于 ADO 对象设计为与 Microsoft Jet 数据库之外的多个数据库配合使用, 因此特定于 Jet 的功能被分解为 JRO 库。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-111">Because ADO objects were designed to work with many databases in addition to Microsoft Jet databases, functionality specific to Jet was broken out into the JRO library.</span></span>

<span data-ttu-id="ab2e1-112">下表列出了每个对象模型所提供的功能并与 DAO 相比较。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-112">The following table lists the functionality provided by each compared to DAO.</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ab2e1-113">功能</span><span class="sxs-lookup"><span data-stu-id="ab2e1-113">Functionality</span></span></p></th>
<th><p><span data-ttu-id="ab2e1-114">DAO</span><span class="sxs-lookup"><span data-stu-id="ab2e1-114">DAO</span></span></p></th>
<th><p><span data-ttu-id="ab2e1-115">ADO1</span><span class="sxs-lookup"><span data-stu-id="ab2e1-115">ADO1</span></span></p></th>
<th><p><span data-ttu-id="ab2e1-116">ADOX2</span><span class="sxs-lookup"><span data-stu-id="ab2e1-116">ADOX2</span></span></p></th>
<th><p><span data-ttu-id="ab2e1-117">JRO</span><span class="sxs-lookup"><span data-stu-id="ab2e1-117">JRO</span></span><br />
<span data-ttu-id="ab2e1-118">(仅限 MDBs)</span><span class="sxs-lookup"><span data-stu-id="ab2e1-118">(MDBs only)</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab2e1-119">创建记录集。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-119">Create Recordsets.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-120">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-120">X</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-121">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-121">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2e1-122">编辑启动属性。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-122">Edit Startup properties.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-123">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-123">X</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-124">X \* \*</span><span class="sxs-lookup"><span data-stu-id="ab2e1-124">X\*\*</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2e1-125">支持遵守 ansi92 SQL. \* \* \*</span><span class="sxs-lookup"><span data-stu-id="ab2e1-125">Support ANSI92 SQL.\*\*\*</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-126">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-126">X</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-127">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-127">X</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2e1-128">创建表。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-128">Create tables.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-129">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-129">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-130">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-130">X</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2e1-131">创建新数据库。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-131">Create new database.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-132">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-132">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-133">版</span><span class="sxs-lookup"><span data-stu-id="ab2e1-133">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2e1-134">编辑现有的表属性。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-134">Edit existing table properties.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-135">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-135">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-136">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-136">X</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2e1-137">创建表关系。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-137">Create table relationships.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-138">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-138">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-139">版</span><span class="sxs-lookup"><span data-stu-id="ab2e1-139">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2e1-140">编辑安全设置。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-140">Edit security settings.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-141">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-142">版</span><span class="sxs-lookup"><span data-stu-id="ab2e1-142">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2e1-143">支持对列数据进行压缩属性。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-143">Support for Compression attribute for column data.</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-144">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-144">X</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2e1-145">编辑存储的、基本的 SQL 查询或视图。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-145">Edit stored, basic SQL queries or views.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-146">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-146">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-147">版</span><span class="sxs-lookup"><span data-stu-id="ab2e1-147">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2e1-148">创建只能通过代码访问的永久查询。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-148">Create permanent queries that are accessible only through code.</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-149">版</span><span class="sxs-lookup"><span data-stu-id="ab2e1-149">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2e1-150">创建通过数据库容器/UI 和代码访问的查询。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-150">Create queries accessible through database container/UI and code.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-151">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-151">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2e1-152">压缩/编码数据库。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-152">Compact/encode database.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-153">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-153">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-154">四</span><span class="sxs-lookup"><span data-stu-id="ab2e1-154">X4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2e1-155">刷新缓存。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-155">Refresh cache.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-156">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-156">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-157">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-157">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2e1-158">使数据库可同步复制。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-158">Make database replicable.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-159">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-159">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-160">X3</span><span class="sxs-lookup"><span data-stu-id="ab2e1-160">X3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2e1-161">生成数据库副本。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-161">Make database replicas.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-162">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-162">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-163">X3</span><span class="sxs-lookup"><span data-stu-id="ab2e1-163">X3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2e1-164">同步副本。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-164">Synchronize replicas.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-165">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-165">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="ab2e1-166">X3</span><span class="sxs-lookup"><span data-stu-id="ab2e1-166">X3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2e1-167">编辑数据库属性。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-167">Edit database properties.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-168">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-168">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2e1-169">创建自定义数据库属性。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-169">Create custom database properties.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-170">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-170">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2e1-171">编辑表列属性。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-171">Edit table column properties.</span></span></p></td>
<td><p><span data-ttu-id="ab2e1-172">X</span><span class="sxs-lookup"><span data-stu-id="ab2e1-172">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ab2e1-p101">\* 仅当使用 Microsoft Access 数据库时才可用。以后的 SQL 提供程序版本可能会在 Microsoft Access 项目 (.adp) 中提供该功能。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-p101">\* Only available when working with Microsoft Access databases. Future versions of the SQL Provider may provide this functionality in Microsoft Access projects (.adp).</span></span>

<span data-ttu-id="ab2e1-175">\*\* 仅当使用 Access 项目时才可用。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-175">\*\* Only available when working with Access projects.</span></span>

<span data-ttu-id="ab2e1-176">\*\*\*虽然 Access 数据库引擎支持某些 ANSI 92 SQL, 但它尚未完全符合遵守 ansi92。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-176">\*\*\* Although the Access database engine does support some ANSI 92 SQL, it is not yet fully ANSI92-compliant.</span></span>

<span data-ttu-id="ab2e1-177">1使用**Connection**对象引用数据库。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-177">1 Uses **Connection** object to reference database.</span></span>

<span data-ttu-id="ab2e1-178">2使用**Catalog**对象引用数据库。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-178">2 Uses **Catalog** object to reference database.</span></span>

<span data-ttu-id="ab2e1-179">3使用**副本**对象引用数据库。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-179">3 Uses **Replica** object to reference database.</span></span>

<span data-ttu-id="ab2e1-180">4使用**JetEngine**对象来引用数据库。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-180">4 Uses **JetEngine** object to reference database.</span></span>


> [!NOTE]
> <span data-ttu-id="ab2e1-181">与 DAO 不同, ADO 和 ADOX 对象可以在除 Jet 之外的数据库中执行标记的操作, 只要这些数据库的提供程序支持该操作。</span><span class="sxs-lookup"><span data-stu-id="ab2e1-181">Unlike DAO, ADO and ADOX objects can perform the marked actions in databases other than Jet as long as the provider for those databases supports that action.</span></span>


