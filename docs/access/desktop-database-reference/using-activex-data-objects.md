---
title: 使用 ActiveX 数据对象
TOCTitle: Using ActiveX Data Objects
ms:assetid: 64055c45-7a27-2296-468a-015362898329
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194969(v=office.15)
ms:contentKeyID: 48545279
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm5285627
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 1f7c57ca785e115e9278145921bf50e8afe870ab
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466652"
---
# <a name="using-activex-data-objects"></a><span data-ttu-id="b7dc2-102">使用 ActiveX 数据对象</span><span class="sxs-lookup"><span data-stu-id="b7dc2-102">Using ActiveX Data Objects</span></span>


<span data-ttu-id="b7dc2-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="b7dc2-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="b7dc2-104">Microsoft Access 提供了三种对象模型，使用 Visual Basic 来创建、维护和管理 Access 数据库及其相关数据时要用到这些对象模型。</span><span class="sxs-lookup"><span data-stu-id="b7dc2-104">Microsoft Access provides three object models to use in the creation, maintaining and managing of your Access databases and their related data by using Visual Basic.</span></span>

## <a name="microsoft-activex-data-objects-ado"></a><span data-ttu-id="b7dc2-105">Microsoft ActiveX 数据对象 (ADO)</span><span class="sxs-lookup"><span data-stu-id="b7dc2-105">Microsoft ActiveX Data Objects (ADO)</span></span>

<span data-ttu-id="b7dc2-106">ADO 包含在给定数据源中创建、维护和删除记录所需的对象。</span><span class="sxs-lookup"><span data-stu-id="b7dc2-106">ADO contains the objects needed to create, maintain, and delete records in a given datasource.</span></span>

## <a name="microsoft-ado-ext-for-ddl-and-security-adox"></a><span data-ttu-id="b7dc2-107">Microsoft ADO Ext. for DDL and Security (ADOX)</span><span class="sxs-lookup"><span data-stu-id="b7dc2-107">Microsoft ADO Ext. for DDL and Security (ADOX)</span></span>

<span data-ttu-id="b7dc2-108">ADOX 除了提供管理安全性所需的对象之外，还提供了新建数据库及其所含对象所需的"数据定义语言 (DDL)"对象。</span><span class="sxs-lookup"><span data-stu-id="b7dc2-108">ADOX provides the Data Definition Language(DDL) objects needed to create a new database and its contained objects in addition to the objects needed to manage security.</span></span>

<span data-ttu-id="b7dc2-109">**Microsoft Jet and Replication Objects 2.5 Library (JRO)**</span><span class="sxs-lookup"><span data-stu-id="b7dc2-109">**Microsoft Jet and Replication Objects 2.5 Library (JRO)**</span></span>

<span data-ttu-id="b7dc2-110">因为 ADO 对象是为了与 Microsoft Jet 数据库以及其他许多数据库一起使用而设计的，所以 Jet 所特有的功能被分解到 JRO 库中。</span><span class="sxs-lookup"><span data-stu-id="b7dc2-110">Since ADO objects were designed to work with many databases in addition to Microsoft Jet databases, functionality specific to Jet was broken out into the JRO library.</span></span>

<span data-ttu-id="b7dc2-111">下表列出了每个对象模型所提供的功能并与 DAO 相比较。</span><span class="sxs-lookup"><span data-stu-id="b7dc2-111">The following table lists the functionality provided by each compared to DAO.</span></span>

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
<th><p><span data-ttu-id="b7dc2-112">功能</span><span class="sxs-lookup"><span data-stu-id="b7dc2-112">Functionality</span></span></p></th>
<th><p><span data-ttu-id="b7dc2-113">DAO</span><span class="sxs-lookup"><span data-stu-id="b7dc2-113">DAO</span></span></p></th>
<th><p><span data-ttu-id="b7dc2-114">ADO1</span><span class="sxs-lookup"><span data-stu-id="b7dc2-114">ADO1</span></span></p></th>
<th><p><span data-ttu-id="b7dc2-115">ADOX2</span><span class="sxs-lookup"><span data-stu-id="b7dc2-115">ADOX2</span></span></p></th>
<th><p><span data-ttu-id="b7dc2-116">JRO</span><span class="sxs-lookup"><span data-stu-id="b7dc2-116">JRO</span></span><br />
<span data-ttu-id="b7dc2-117">(仅限于 mdb)</span><span class="sxs-lookup"><span data-stu-id="b7dc2-117">(MDB's Only)</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7dc2-118">创建记录集</span><span class="sxs-lookup"><span data-stu-id="b7dc2-118">Create Recordsets</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-119">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-119">X</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-120">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-120">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dc2-121">编辑“启动”属性</span><span class="sxs-lookup"><span data-stu-id="b7dc2-121">Edit Startup properties</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-122">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-122">X</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-123">X\*\*</span><span class="sxs-lookup"><span data-stu-id="b7dc2-123">X\*\*</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dc2-124">支持 ANSI92 SQL\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b7dc2-124">Support ANSI92 SQL\*\*\*</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-125">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-125">X</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-126">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-126">X</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dc2-127">创建表</span><span class="sxs-lookup"><span data-stu-id="b7dc2-127">Create Tables</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-128">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-128">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-129">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-129">X</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dc2-130">新建数据库</span><span class="sxs-lookup"><span data-stu-id="b7dc2-130">Create New Database</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-131">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-131">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-132">X\*</span><span class="sxs-lookup"><span data-stu-id="b7dc2-132">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dc2-133">编辑现有表属性</span><span class="sxs-lookup"><span data-stu-id="b7dc2-133">Edit Existing Table properties</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-134">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-134">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-135">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-135">X</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dc2-136">创建表关系</span><span class="sxs-lookup"><span data-stu-id="b7dc2-136">Create table relationships</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-137">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-138">X\*</span><span class="sxs-lookup"><span data-stu-id="b7dc2-138">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dc2-139">编辑安全设置</span><span class="sxs-lookup"><span data-stu-id="b7dc2-139">Edit security settings</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-140">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-140">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-141">X\*</span><span class="sxs-lookup"><span data-stu-id="b7dc2-141">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dc2-142">对列数据的“压缩”属性的支持</span><span class="sxs-lookup"><span data-stu-id="b7dc2-142">Support for Compression attribute for column data</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-143">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-143">X</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dc2-144">编辑已保存、基本 SQL 查询或视图</span><span class="sxs-lookup"><span data-stu-id="b7dc2-144">Edit stored, basic SQL queries or views</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-145">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-145">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-146">X\*</span><span class="sxs-lookup"><span data-stu-id="b7dc2-146">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dc2-147">创建只能通过代码访问的永久查询。</span><span class="sxs-lookup"><span data-stu-id="b7dc2-147">Create permanent queries that are accessible only through code.</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-148">X\*</span><span class="sxs-lookup"><span data-stu-id="b7dc2-148">X\*</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dc2-149">创建通过数据库容器/UI 和代码访问的查询。</span><span class="sxs-lookup"><span data-stu-id="b7dc2-149">Create queries accessible through database container/UI and code.</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-150">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-150">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dc2-151">压缩/编码数据库</span><span class="sxs-lookup"><span data-stu-id="b7dc2-151">Compact/Encode database</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-152">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-152">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-153">X4</span><span class="sxs-lookup"><span data-stu-id="b7dc2-153">X4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dc2-154">刷新缓存</span><span class="sxs-lookup"><span data-stu-id="b7dc2-154">Refresh Cache</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-155">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-155">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-156">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-156">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dc2-157">使得数据库可复制</span><span class="sxs-lookup"><span data-stu-id="b7dc2-157">Make Database Replicable</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-158">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-158">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-159">X3</span><span class="sxs-lookup"><span data-stu-id="b7dc2-159">X3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dc2-160">制作数据库副本</span><span class="sxs-lookup"><span data-stu-id="b7dc2-160">Make Database Replicas</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-161">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-161">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-162">X3</span><span class="sxs-lookup"><span data-stu-id="b7dc2-162">X3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dc2-163">使副本同步</span><span class="sxs-lookup"><span data-stu-id="b7dc2-163">Synchronize Replicas</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-164">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-164">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="b7dc2-165">X3</span><span class="sxs-lookup"><span data-stu-id="b7dc2-165">X3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dc2-166">编辑数据库属性</span><span class="sxs-lookup"><span data-stu-id="b7dc2-166">Edit Database properties</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-167">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-167">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7dc2-168">创建自定义数据库属性</span><span class="sxs-lookup"><span data-stu-id="b7dc2-168">Create custom database properties</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-169">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-169">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7dc2-170">编辑表列属性</span><span class="sxs-lookup"><span data-stu-id="b7dc2-170">Edit table column properties</span></span></p></td>
<td><p><span data-ttu-id="b7dc2-171">X</span><span class="sxs-lookup"><span data-stu-id="b7dc2-171">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b7dc2-p101">\* 仅当使用 Microsoft Access 数据库时才可用。以后的 SQL 提供程序版本可能会在 Microsoft Access 项目 (.adp) 中提供该功能。</span><span class="sxs-lookup"><span data-stu-id="b7dc2-p101">\* Only available when working with Microsoft Access databases. Future versions of the SQL Provider may provide this functionality in Microsoft Access projects (.adp).</span></span>

<span data-ttu-id="b7dc2-174">\*\* 仅当使用 Access 项目时才可用。</span><span class="sxs-lookup"><span data-stu-id="b7dc2-174">\*\* Only available when working with Access projects.</span></span>

<span data-ttu-id="b7dc2-175">\*\*\* 尽管 Access 数据库引擎支持某些 ANSI 92 SQL，但它仍然不能完全遵守 ANSI92。</span><span class="sxs-lookup"><span data-stu-id="b7dc2-175">\*\*\* Though the Access database engine does support some ANSI 92 SQL it is not yet fully ANSI92 compliant.</span></span>

<span data-ttu-id="b7dc2-176">1使用 **Connection** 对象来引用数据库</span><span class="sxs-lookup"><span data-stu-id="b7dc2-176">1 Uses **Connection** object to reference to database</span></span>

<span data-ttu-id="b7dc2-177">2使用 **Catalog** 对象来引用数据库</span><span class="sxs-lookup"><span data-stu-id="b7dc2-177">2 Uses **Catalog** object to reference database</span></span>

<span data-ttu-id="b7dc2-178">3使用 **Replica** 对象来引用数据库</span><span class="sxs-lookup"><span data-stu-id="b7dc2-178">3 Uses **Replica** object to reference database</span></span>

<span data-ttu-id="b7dc2-179">4使用 **JetEngine** 对象来引用数据库</span><span class="sxs-lookup"><span data-stu-id="b7dc2-179">4 Uses **JetEngine** object to reference database</span></span>


> [!NOTE]
> <P><span data-ttu-id="b7dc2-180">[!注释] 与 DAO 不同，ADO 和 ADOX 对象可以在非 Jet 数据库中执行所标出的操作（只要这些数据库的提供程序支持该操作）。</span><span class="sxs-lookup"><span data-stu-id="b7dc2-180">Unlike DAO, ADO and ADOX objects can perform the marked actions in databases other then Jet as long as the provider for those databases supports that action.</span></span></P>


