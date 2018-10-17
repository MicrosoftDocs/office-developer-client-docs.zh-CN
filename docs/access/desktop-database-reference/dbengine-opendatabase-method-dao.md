---
title: DBEngine.OpenDatabase Method (DAO)
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
ms.openlocfilehash: 6999c003883675837ad333b6488820f3bb3a9f2e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468663"
---
# <a name="dbengineopendatabase-method-dao"></a><span data-ttu-id="8b574-102">DBEngine.OpenDatabase Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="8b574-102">DBEngine.OpenDatabase Method (DAO)</span></span>


<span data-ttu-id="8b574-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8b574-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8b574-104">打开指定的数据库，并返回一个指向代表该数据库的 **[Database](database-object-dao.md)** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="8b574-104">Opens a specified database and returns a reference to the **[Database](database-object-dao.md)** object that represents it.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b574-105">语法</span><span class="sxs-lookup"><span data-stu-id="8b574-105">Syntax</span></span>

<span data-ttu-id="8b574-106">*表达式*。OpenDatabase （***名称***、***选项***、 ***ReadOnly***、***连接***）</span><span class="sxs-lookup"><span data-stu-id="8b574-106">*expression* .OpenDatabase(***Name***, ***Options***, ***ReadOnly***, ***Connect***)</span></span>

<span data-ttu-id="8b574-107">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="8b574-107">*expression* A variable that represents a **DBEngine** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="8b574-108">参数</span><span class="sxs-lookup"><span data-stu-id="8b574-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8b574-109">名称</span><span class="sxs-lookup"><span data-stu-id="8b574-109">Name</span></span></p></th>
<th><p><span data-ttu-id="8b574-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="8b574-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="8b574-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="8b574-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="8b574-112">说明</span><span class="sxs-lookup"><span data-stu-id="8b574-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b574-113">名称</span><span class="sxs-lookup"><span data-stu-id="8b574-113">Name</span></span></p></td>
<td><p><span data-ttu-id="8b574-114">必需</span><span class="sxs-lookup"><span data-stu-id="8b574-114">Required</span></span></p></td>
<td><p><span data-ttu-id="8b574-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="8b574-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="8b574-p101">现有 Microsoft Access 数据库文件的名称，或者 ODBC 数据源的数据源名称 (DSN)。有关设置此值的详细信息，请参阅 <strong><a href="connection-name-property-dao.md">Name</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="8b574-p101">the name of an existing Microsoft Access database file, or the data source name (DSN) of an ODBC data source. See the <strong><a href="connection-name-property-dao.md">Name</a></strong> property for more information about setting this value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b574-118">选项</span><span class="sxs-lookup"><span data-stu-id="8b574-118">Options</span></span></p></td>
<td><p><span data-ttu-id="8b574-119">可选</span><span class="sxs-lookup"><span data-stu-id="8b574-119">Optional</span></span></p></td>
<td><p><span data-ttu-id="8b574-120"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="8b574-120"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="8b574-121">根据“说明”中的指定设置数据库的各个选项。</span><span class="sxs-lookup"><span data-stu-id="8b574-121">Sets various options for the database, as specified in Remarks.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b574-122">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="8b574-122">ReadOnly</span></span></p></td>
<td><p><span data-ttu-id="8b574-123">可选</span><span class="sxs-lookup"><span data-stu-id="8b574-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="8b574-124"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="8b574-124"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="8b574-125">						如果要使用只读访问权限打开数据库，此值为 <strong>True</strong>；如果要使用可读写访问权限打开数据库，此值为 <strong>False</strong>（默认值）。</span><span class="sxs-lookup"><span data-stu-id="8b574-125"><strong>True</strong> if you want to open the database with read-only access, or <strong>False</strong> (default) if you want to open the database with read/write access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b574-126">在浏览器中</span><span class="sxs-lookup"><span data-stu-id="8b574-126">Connect</span></span></p></td>
<td><p><span data-ttu-id="8b574-127">可选</span><span class="sxs-lookup"><span data-stu-id="8b574-127">Optional</span></span></p></td>
<td><p><span data-ttu-id="8b574-128"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="8b574-128"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="8b574-129">指定包括密码在内的各种连接信息。</span><span class="sxs-lookup"><span data-stu-id="8b574-129">Specifies various connection information, including passwords.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="return-value"></a><span data-ttu-id="8b574-130">返回值</span><span class="sxs-lookup"><span data-stu-id="8b574-130">Return Value</span></span>

<span data-ttu-id="8b574-131">Database</span><span class="sxs-lookup"><span data-stu-id="8b574-131">Database</span></span>

## <a name="remarks"></a><span data-ttu-id="8b574-132">注解</span><span class="sxs-lookup"><span data-stu-id="8b574-132">Remarks</span></span>

<span data-ttu-id="8b574-133">可以为 options 参数使用以下值。</span><span class="sxs-lookup"><span data-stu-id="8b574-133">You can use the following values for the options argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8b574-134">设置</span><span class="sxs-lookup"><span data-stu-id="8b574-134">Setting</span></span></p></th>
<th><p><span data-ttu-id="8b574-135">说明</span><span class="sxs-lookup"><span data-stu-id="8b574-135">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b574-136"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="8b574-136"><strong>True</strong></span></span></p></td>
<td><p><span data-ttu-id="8b574-137">以独占模式打开数据库。</span><span class="sxs-lookup"><span data-stu-id="8b574-137">Opens the database in exclusive mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b574-138"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="8b574-138"><strong>False</strong></span></span></p></td>
<td><p><span data-ttu-id="8b574-139">（默认值）以共享模式打开数据库。</span><span class="sxs-lookup"><span data-stu-id="8b574-139">(Default) Opens the database in shared mode.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b574-140">打开一个数据库后，该数据库将自动添加到 **Databases** 连接。</span><span class="sxs-lookup"><span data-stu-id="8b574-140">When you open a database, it is automatically added to the **Databases** collection.</span></span>

<span data-ttu-id="8b574-141">使用 dbname 时，一些事项：</span><span class="sxs-lookup"><span data-stu-id="8b574-141">Some considerations apply when you use dbname:</span></span>

  - <span data-ttu-id="8b574-142">如果它引用了已打开以便由其他用户访问的数据库，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="8b574-142">If it refers to a database that is already open for access by another user, an error occurs.</span></span>

  - <span data-ttu-id="8b574-143">如果它没有引用现有数据库或有效的 ODBC 数据源名称，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="8b574-143">If it doesn't refer to an existing database or valid ODBC data source name, an error occurs.</span></span>

  - <span data-ttu-id="8b574-144">如果它是零长度字符串 ("") 并且*连接*是"ODBC;"，以便用户可以选择数据库，则显示一个对话框，列出所有已注册的 ODBC 数据源名称。</span><span class="sxs-lookup"><span data-stu-id="8b574-144">If it's a zero-length string ("") and *connect* is "ODBC;" , a dialog box listing all registered ODBC data source names is displayed so the user can select a database.</span></span>

<span data-ttu-id="8b574-145">若要关闭数据库，以便从 **Databases** 集合中删除 **Database** 对象，请对该对象使用 **[Close](connection-close-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="8b574-145">To close a database, and thus remove the **Database** object from the **Databases** collection, use the **[Close](connection-close-method-dao.md)** method on the object.</span></span>


> [!NOTE]
> <P><span data-ttu-id="8b574-146">[!注释] 在访问 Microsoft Access 数据库引擎连接的 ODBC 数据源时，可通过打开连接到 ODBC 数据源的 <STRONG>Database</STRONG> 对象改善应用程序的性能，这样不需要将单个 <STRONG><A href="tabledef-object-dao.md">TableDef</A></STRONG> 对象链接到 ODBC 数据源中的特定表。</span><span class="sxs-lookup"><span data-stu-id="8b574-146">When you access a Microsoft Access database engine-connected ODBC data source, you can improve your application's performance by opening a <STRONG>Database</STRONG> object connected to the ODBC data source, rather than by linking individual <STRONG><A href="tabledef-object-dao.md">TableDef</A></STRONG> objects to specific tables in the ODBC data source.</span></span></P>

