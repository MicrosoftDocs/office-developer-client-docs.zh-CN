---
title: DBEngine.OpenDatabase 方法 (DAO)
TOCTitle: OpenDatabase Method
ms:assetid: 49fca321-5955-3e69-64ea-da191536eadb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193474(v=office.15)
ms:contentKeyID: 48544654
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052979
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 1cd4188931999284a6454064a0906b64cf1f519a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294251"
---
# <a name="dbengineopendatabase-method-dao"></a><span data-ttu-id="08d8d-102">DBEngine.OpenDatabase 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="08d8d-102">DBEngine.OpenDatabase method (DAO)</span></span>

<span data-ttu-id="08d8d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="08d8d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="08d8d-104">打开指定的数据库并返回对表示该数据库的 **[Database](database-object-dao.md)** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="08d8d-104">Opens a specified database and returns a reference to the **[Database](database-object-dao.md)** object that represents it.</span></span>

## <a name="syntax"></a><span data-ttu-id="08d8d-105">语法</span><span class="sxs-lookup"><span data-stu-id="08d8d-105">Syntax</span></span>

<span data-ttu-id="08d8d-106">*表达式* .OpenDatabase(***Name***, ***Options***, ***ReadOnly***, ***Connect***)</span><span class="sxs-lookup"><span data-stu-id="08d8d-106">*expression* .OpenDatabase(***Name***, ***Options***, ***ReadOnly***, ***Connect***)</span></span>

<span data-ttu-id="08d8d-107">*表达式* 一个表示 **DBEngine** 对象的变量。</span><span class="sxs-lookup"><span data-stu-id="08d8d-107">*expression*  A variable that represents a **DBEngine** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="08d8d-108">参数</span><span class="sxs-lookup"><span data-stu-id="08d8d-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="08d8d-109">名称</span><span class="sxs-lookup"><span data-stu-id="08d8d-109">Name</span></span></p></th>
<th><p><span data-ttu-id="08d8d-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="08d8d-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="08d8d-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="08d8d-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="08d8d-112">说明</span><span class="sxs-lookup"><span data-stu-id="08d8d-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08d8d-113"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="08d8d-113"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="08d8d-114">必需</span><span class="sxs-lookup"><span data-stu-id="08d8d-114">Required</span></span></p></td>
<td><p><span data-ttu-id="08d8d-115"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="08d8d-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="08d8d-116">现有 Microsoft Access 数据库文件的名称或 ODBC 数据源的数据源名称 (DSN)。</span><span class="sxs-lookup"><span data-stu-id="08d8d-116">the name of an existing Microsoft Access database file, or the data source name (DSN) of an ODBC data source.</span></span> <span data-ttu-id="08d8d-117">有关设置此值的详细信息，请参阅 <strong><a href="connection-name-property-dao.md">Name</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="08d8d-117">See the <a href="connection-name-property-dao.md"><strong>Name</strong></a> property for more information about setting this value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d8d-118"><em>选项</em></span><span class="sxs-lookup"><span data-stu-id="08d8d-118"><em>Options</em></span></span></p></td>
<td><p><span data-ttu-id="08d8d-119">可选</span><span class="sxs-lookup"><span data-stu-id="08d8d-119">Optional</span></span></p></td>
<td><p><span data-ttu-id="08d8d-120"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="08d8d-120"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="08d8d-121">设置数据库的各种选项（如“说明”中所述）。</span><span class="sxs-lookup"><span data-stu-id="08d8d-121">Sets various options for the database, as specified in Remarks.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08d8d-122"><em>ReadOnly</em></span><span class="sxs-lookup"><span data-stu-id="08d8d-122"><em>ReadOnly</em></span></span></p></td>
<td><p><span data-ttu-id="08d8d-123">可选</span><span class="sxs-lookup"><span data-stu-id="08d8d-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="08d8d-124"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="08d8d-124"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="08d8d-125">如果要使用只读访问权限打开数据库，此值为 <strong>True</strong>；如果要使用可读写访问权限打开数据库，此值为 <strong>False</strong>（默认值）。</span><span class="sxs-lookup"><span data-stu-id="08d8d-125"><strong>True</strong> if you want to open the database with read-only access, or <strong>False</strong> (default) if you want to open the database with read/write access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d8d-126"><em>Connect</em></span><span class="sxs-lookup"><span data-stu-id="08d8d-126"><em>Connect</em></span></span></p></td>
<td><p><span data-ttu-id="08d8d-127">可选</span><span class="sxs-lookup"><span data-stu-id="08d8d-127">Optional</span></span></p></td>
<td><p><span data-ttu-id="08d8d-128"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="08d8d-128"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="08d8d-129">指定各种连接信息，包括密码。</span><span class="sxs-lookup"><span data-stu-id="08d8d-129">Specifies various connection information, including passwords.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="08d8d-130">返回值</span><span class="sxs-lookup"><span data-stu-id="08d8d-130">Return value</span></span>

<span data-ttu-id="08d8d-131">Database</span><span class="sxs-lookup"><span data-stu-id="08d8d-131">Database</span></span>

## <a name="remarks"></a><span data-ttu-id="08d8d-132">说明</span><span class="sxs-lookup"><span data-stu-id="08d8d-132">Remarks</span></span>

<span data-ttu-id="08d8d-133">可以为 Options 参数使用如下值。</span><span class="sxs-lookup"><span data-stu-id="08d8d-133">You can use the following values for the options argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="08d8d-134">Setting</span><span class="sxs-lookup"><span data-stu-id="08d8d-134">Setting</span></span></p></th>
<th><p><span data-ttu-id="08d8d-135">说明</span><span class="sxs-lookup"><span data-stu-id="08d8d-135">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08d8d-136"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="08d8d-136"><strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="08d8d-137">以独占模式打开数据库。</span><span class="sxs-lookup"><span data-stu-id="08d8d-137">Opens the database in exclusive mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08d8d-138"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="08d8d-138"><strong>False</strong></span></span></p></td>
<td><p><span data-ttu-id="08d8d-139">（默认）以共享模式打开数据库。</span><span class="sxs-lookup"><span data-stu-id="08d8d-139">(Default) Opens the database in shared mode.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="08d8d-140">打开数据库时会自动将该数据库添加到 **Databases** 集合。</span><span class="sxs-lookup"><span data-stu-id="08d8d-140">When you open a database, it is automatically added to the **Databases** collection.</span></span>

<span data-ttu-id="08d8d-141">使用 dbname 时有以下适用的注意事项：</span><span class="sxs-lookup"><span data-stu-id="08d8d-141">Some considerations apply when you use  dbname:</span></span>

- <span data-ttu-id="08d8d-142">如果它引用了已打开以便由其他用户访问的数据库，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="08d8d-142">If it refers to a database that is already open for access by another user, an error occurs.</span></span>

- <span data-ttu-id="08d8d-143">如果它没有引用现有数据库或有效的 ODBC 数据源名称，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="08d8d-143">If it doesn't refer to an existing database or valid ODBC data source name, an error occurs.</span></span>

- <span data-ttu-id="08d8d-144">如果它是零长度字符串 ("")，并且 *connect* 为 "ODBC;"，则会显示列出所有已注册 ODBC 数据源名称的对话框，以便用户能够选择数据库。</span><span class="sxs-lookup"><span data-stu-id="08d8d-144">If it's a zero-length string ("") and connect is "ODBC;"
, a dialog box listing all registered ODBC data source names is displayed so the user can select a database.</span></span>

<span data-ttu-id="08d8d-145">若要关闭一个数据库，并因此从 **Databases** 集合中删除 **Database** 对象，请对该对象使用 **[Close](connection-close-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="08d8d-145">To close a database, and thus remove the **Database** object from the **Databases** collection, use the **[Close](connection-close-method-dao.md)** method on the object.</span></span>

> [!NOTE]
> <span data-ttu-id="08d8d-146">[!注释] 在访问 Microsoft Access 数据库引擎连接的 ODBC 数据源时，可通过打开连接到 ODBC 数据源的 **Database** 对象改善应用程序的性能，这样不需要将单个 [TableDef](tabledef-object-dao.md) 对象链接到 ODBC 数据源中的特定表。</span><span class="sxs-lookup"><span data-stu-id="08d8d-146">When you access a Microsoft Access database engine-connected ODBC data source, you can improve your application's performance by opening a **Database** object connected to the ODBC data source, rather than by linking individual [TableDef](tabledef-object-dao.md) objects to specific tables in the ODBC data source.</span></span>


