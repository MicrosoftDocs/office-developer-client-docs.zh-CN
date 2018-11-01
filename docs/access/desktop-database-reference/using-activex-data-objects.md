---
title: 使用 ActiveX 数据对象
TOCTitle: Use ActiveX Data Objects
description: Microsoft Access 提供了三个对象模型用于创建、 维护和管理 Access 数据库及其相关的数据的使用 Visual Basic。
ms:assetid: 64055c45-7a27-2296-468a-015362898329
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194969(v=office.15)
ms:contentKeyID: 48545279
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm5285627
f1_categories:
- Office.Version=v15
ms.openlocfilehash: d7e8e7e6abeea9cca86c928760eddb990517a207
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887507"
---
# <a name="use-activex-data-objects"></a><span data-ttu-id="2b044-103">使用 ActiveX 数据对象</span><span class="sxs-lookup"><span data-stu-id="2b044-103">Use ActiveX Data Objects</span></span>

<span data-ttu-id="2b044-104">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2b044-104">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2b044-105">Microsoft Access 提供了三个对象模型用于创建、 维护和管理 Access 数据库及其相关的数据的使用 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="2b044-105">Microsoft Access provides three object models to use in the creation, maintaining, and managing of your Access databases and their related data by using Visual Basic.</span></span>

## <a name="microsoft-activex-data-objects-ado"></a><span data-ttu-id="2b044-106">Microsoft ActiveX 数据对象 (ADO)</span><span class="sxs-lookup"><span data-stu-id="2b044-106">Microsoft ActiveX Data Objects (ADO)</span></span>

<span data-ttu-id="2b044-107">ADO 包含在给定数据源中创建、维护和删除记录所需的对象。</span><span class="sxs-lookup"><span data-stu-id="2b044-107">ADO contains the objects needed to create, maintain, and delete records in a given datasource.</span></span>

## <a name="microsoft-ado-ext-for-ddl-and-security-adox"></a><span data-ttu-id="2b044-108">Microsoft ADO 分机 DDL 和安全性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="2b044-108">Microsoft ADO ext. for DDL and security (ADOX)</span></span>

<span data-ttu-id="2b044-109">ADOX 提供所需创建一个新数据库的数据定义语言 (DDL) 对象和管理安全性所需的对象除了其所含的对象。</span><span class="sxs-lookup"><span data-stu-id="2b044-109">ADOX provides the Data Definition Language (DDL) objects needed to create a new database and its contained objects in addition to the objects needed to manage security.</span></span>

### <a name="microsoft-jet-and-replication-objects-25-library-jro"></a><span data-ttu-id="2b044-110">Microsoft Jet 和复制对象 2.5 库 (JRO)</span><span class="sxs-lookup"><span data-stu-id="2b044-110">Microsoft Jet and Replication Objects 2.5 library (JRO)</span></span>

<span data-ttu-id="2b044-111">因为 ADO 对象已旨在能够使用 Microsoft Jet 数据库许多数据库，特定于 Jet 功能被分解到 JRO 库。</span><span class="sxs-lookup"><span data-stu-id="2b044-111">Because ADO objects were designed to work with many databases in addition to Microsoft Jet databases, functionality specific to Jet was broken out into the JRO library.</span></span>

<span data-ttu-id="2b044-112">下表列出了每个对象模型所提供的功能并与 DAO 相比较。</span><span class="sxs-lookup"><span data-stu-id="2b044-112">The following table lists the functionality provided by each compared to DAO.</span></span>

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
<th><p><span data-ttu-id="2b044-113">功能</span><span class="sxs-lookup"><span data-stu-id="2b044-113">Functionality</span></span></p></th>
<th><p><span data-ttu-id="2b044-114">DAO</span><span class="sxs-lookup"><span data-stu-id="2b044-114">DAO</span></span></p></th>
<th><p><span data-ttu-id="2b044-115">ADO1</span><span class="sxs-lookup"><span data-stu-id="2b044-115">ADO1</span></span></p></th>
<th><p><span data-ttu-id="2b044-116">ADOX2</span><span class="sxs-lookup"><span data-stu-id="2b044-116">ADOX2</span></span></p></th>
<th><p><span data-ttu-id="2b044-117">JRO</span><span class="sxs-lookup"><span data-stu-id="2b044-117">JRO</span></span><br />
<span data-ttu-id="2b044-118">(仅适用于 Mdb)</span><span class="sxs-lookup"><span data-stu-id="2b044-118">(MDBs only)</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b044-119">创建记录集。</span><span class="sxs-lookup"><span data-stu-id="2b044-119">Create Recordsets.</span></span></p></td>
<td><p><span data-ttu-id="2b044-120">X</span><span class="sxs-lookup"><span data-stu-id="2b044-120">X</span></span></p></td>
<td><p><span data-ttu-id="2b044-121">X</span><span class="sxs-lookup"><span data-stu-id="2b044-121">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b044-122">编辑启动属性。</span><span class="sxs-lookup"><span data-stu-id="2b044-122">Edit Startup properties.</span></span></p></td>
<td><p><span data-ttu-id="2b044-123">X</span><span class="sxs-lookup"><span data-stu-id="2b044-123">X</span></span></p></td>
<td><p><span data-ttu-id="2b044-124">X\*\*</span><span class="sxs-lookup"><span data-stu-id="2b044-124">X\*\*</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b044-125">支持 ANSI92 SQL.\* \* \*</span><span class="sxs-lookup"><span data-stu-id="2b044-125">Support ANSI92 SQL.\*\*\*</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-126">X</span><span class="sxs-lookup"><span data-stu-id="2b044-126">X</span></span></p></td>
<td><p><span data-ttu-id="2b044-127">X</span><span class="sxs-lookup"><span data-stu-id="2b044-127">X</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b044-128">创建表。</span><span class="sxs-lookup"><span data-stu-id="2b044-128">Create tables.</span></span></p></td>
<td><p><span data-ttu-id="2b044-129">X</span><span class="sxs-lookup"><span data-stu-id="2b044-129">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-130">X</span><span class="sxs-lookup"><span data-stu-id="2b044-130">X</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b044-131">创建新数据库。</span><span class="sxs-lookup"><span data-stu-id="2b044-131">Create new database.</span></span></p></td>
<td><p><span data-ttu-id="2b044-132">X</span><span class="sxs-lookup"><span data-stu-id="2b044-132">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-133">X\*</span><span class="sxs-lookup"><span data-stu-id="2b044-133">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b044-134">编辑现有表属性。</span><span class="sxs-lookup"><span data-stu-id="2b044-134">Edit existing table properties.</span></span></p></td>
<td><p><span data-ttu-id="2b044-135">X</span><span class="sxs-lookup"><span data-stu-id="2b044-135">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-136">X</span><span class="sxs-lookup"><span data-stu-id="2b044-136">X</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b044-137">创建表关系。</span><span class="sxs-lookup"><span data-stu-id="2b044-137">Create table relationships.</span></span></p></td>
<td><p><span data-ttu-id="2b044-138">X</span><span class="sxs-lookup"><span data-stu-id="2b044-138">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-139">X\*</span><span class="sxs-lookup"><span data-stu-id="2b044-139">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b044-140">编辑安全设置。</span><span class="sxs-lookup"><span data-stu-id="2b044-140">Edit security settings.</span></span></p></td>
<td><p><span data-ttu-id="2b044-141">X</span><span class="sxs-lookup"><span data-stu-id="2b044-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-142">X\*</span><span class="sxs-lookup"><span data-stu-id="2b044-142">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b044-143">支持对列数据压缩属性。</span><span class="sxs-lookup"><span data-stu-id="2b044-143">Support for Compression attribute for column data.</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-144">X</span><span class="sxs-lookup"><span data-stu-id="2b044-144">X</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b044-145">编辑保存、 基本 SQL 查询或视图。</span><span class="sxs-lookup"><span data-stu-id="2b044-145">Edit stored, basic SQL queries or views.</span></span></p></td>
<td><p><span data-ttu-id="2b044-146">X</span><span class="sxs-lookup"><span data-stu-id="2b044-146">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-147">X\*</span><span class="sxs-lookup"><span data-stu-id="2b044-147">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b044-148">创建只能通过代码访问的永久查询。</span><span class="sxs-lookup"><span data-stu-id="2b044-148">Create permanent queries that are accessible only through code.</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-149">X\*</span><span class="sxs-lookup"><span data-stu-id="2b044-149">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b044-150">创建通过数据库容器/UI 和代码访问的查询。</span><span class="sxs-lookup"><span data-stu-id="2b044-150">Create queries accessible through database container/UI and code.</span></span></p></td>
<td><p><span data-ttu-id="2b044-151">X</span><span class="sxs-lookup"><span data-stu-id="2b044-151">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b044-152">压缩/编码数据库。</span><span class="sxs-lookup"><span data-stu-id="2b044-152">Compact/encode database.</span></span></p></td>
<td><p><span data-ttu-id="2b044-153">X</span><span class="sxs-lookup"><span data-stu-id="2b044-153">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-154">X4</span><span class="sxs-lookup"><span data-stu-id="2b044-154">X4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b044-155">刷新缓存。</span><span class="sxs-lookup"><span data-stu-id="2b044-155">Refresh cache.</span></span></p></td>
<td><p><span data-ttu-id="2b044-156">X</span><span class="sxs-lookup"><span data-stu-id="2b044-156">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-157">X</span><span class="sxs-lookup"><span data-stu-id="2b044-157">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b044-158">使数据库变为可复制。</span><span class="sxs-lookup"><span data-stu-id="2b044-158">Make database replicable.</span></span></p></td>
<td><p><span data-ttu-id="2b044-159">X</span><span class="sxs-lookup"><span data-stu-id="2b044-159">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-160">X3</span><span class="sxs-lookup"><span data-stu-id="2b044-160">X3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b044-161">制作数据库副本。</span><span class="sxs-lookup"><span data-stu-id="2b044-161">Make database replicas.</span></span></p></td>
<td><p><span data-ttu-id="2b044-162">X</span><span class="sxs-lookup"><span data-stu-id="2b044-162">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-163">X3</span><span class="sxs-lookup"><span data-stu-id="2b044-163">X3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b044-164">将副本同步。</span><span class="sxs-lookup"><span data-stu-id="2b044-164">Synchronize replicas.</span></span></p></td>
<td><p><span data-ttu-id="2b044-165">X</span><span class="sxs-lookup"><span data-stu-id="2b044-165">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="2b044-166">X3</span><span class="sxs-lookup"><span data-stu-id="2b044-166">X3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b044-167">编辑数据库属性。</span><span class="sxs-lookup"><span data-stu-id="2b044-167">Edit database properties.</span></span></p></td>
<td><p><span data-ttu-id="2b044-168">X</span><span class="sxs-lookup"><span data-stu-id="2b044-168">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b044-169">创建自定义数据库属性。</span><span class="sxs-lookup"><span data-stu-id="2b044-169">Create custom database properties.</span></span></p></td>
<td><p><span data-ttu-id="2b044-170">X</span><span class="sxs-lookup"><span data-stu-id="2b044-170">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b044-171">编辑表列属性。</span><span class="sxs-lookup"><span data-stu-id="2b044-171">Edit table column properties.</span></span></p></td>
<td><p><span data-ttu-id="2b044-172">X</span><span class="sxs-lookup"><span data-stu-id="2b044-172">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2b044-p101">\* 仅当使用 Microsoft Access 数据库时才可用。以后的 SQL 提供程序版本可能会在 Microsoft Access 项目 (.adp) 中提供该功能。</span><span class="sxs-lookup"><span data-stu-id="2b044-p101">\* Only available when working with Microsoft Access databases. Future versions of the SQL Provider may provide this functionality in Microsoft Access projects (.adp).</span></span>

<span data-ttu-id="2b044-175">\*\* 仅当使用 Access 项目时才可用。</span><span class="sxs-lookup"><span data-stu-id="2b044-175">\*\* Only available when working with Access projects.</span></span>

<span data-ttu-id="2b044-176">\*\*\*尽管 Access 数据库引擎支持某些 ANSI 92 SQL，但它尚未完全遵守 ANSI92。</span><span class="sxs-lookup"><span data-stu-id="2b044-176">\*\*\* Although the Access database engine does support some ANSI 92 SQL, it is not yet fully ANSI92-compliant.</span></span>

<span data-ttu-id="2b044-177">1 使用**Connection**对象来引用数据库。</span><span class="sxs-lookup"><span data-stu-id="2b044-177">1 Uses **Connection** object to reference database.</span></span>

<span data-ttu-id="2b044-178">使用**Catalog**对象来引用数据库 2。</span><span class="sxs-lookup"><span data-stu-id="2b044-178">2 Uses **Catalog** object to reference database.</span></span>

<span data-ttu-id="2b044-179">3 使用**副本**对象来引用数据库。</span><span class="sxs-lookup"><span data-stu-id="2b044-179">3 Uses **Replica** object to reference database.</span></span>

<span data-ttu-id="2b044-180">4 使用**JetEngine**对象来引用数据库。</span><span class="sxs-lookup"><span data-stu-id="2b044-180">4 Uses **JetEngine** object to reference database.</span></span>


> [!NOTE]
> <span data-ttu-id="2b044-181">与 DAO，不同 ADO 和 ADOX 对象可以执行标记的操作之外 Jet 数据库中，只要这些数据库的提供程序支持的操作。</span><span class="sxs-lookup"><span data-stu-id="2b044-181">Unlike DAO, ADO and ADOX objects can perform the marked actions in databases other than Jet as long as the provider for those databases supports that action.</span></span>


