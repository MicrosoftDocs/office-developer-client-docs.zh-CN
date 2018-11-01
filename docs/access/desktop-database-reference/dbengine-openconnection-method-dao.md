---
title: DBEngine.OpenConnection Method (DAO)
TOCTitle: OpenConnection Method
ms:assetid: 778a581f-be42-94ee-e5c6-4cbc1843450d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196074(v=office.15)
ms:contentKeyID: 48545729
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053574
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 959291193b8606ce223e6ad1a20c17895b136a13
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876790"
---
# <a name="dbengineopenconnection-method-dao"></a><span data-ttu-id="18442-102">DBEngine.OpenConnection Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="18442-102">DBEngine.OpenConnection Method (DAO)</span></span>


<span data-ttu-id="18442-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="18442-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="18442-104">语法</span><span class="sxs-lookup"><span data-stu-id="18442-104">Syntax</span></span>

<span data-ttu-id="18442-105">*表达式*。OpenConnection （***名称***、***选项***、 ***ReadOnly***、***连接***）</span><span class="sxs-lookup"><span data-stu-id="18442-105">*expression* .OpenConnection(***Name***, ***Options***, ***ReadOnly***, ***Connect***)</span></span>

<span data-ttu-id="18442-106">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="18442-106">*expression* A variable that represents a **DBEngine** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="18442-107">参数</span><span class="sxs-lookup"><span data-stu-id="18442-107">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="18442-108">名称</span><span class="sxs-lookup"><span data-stu-id="18442-108">Name</span></span></p></th>
<th><p><span data-ttu-id="18442-109">必需/可选</span><span class="sxs-lookup"><span data-stu-id="18442-109">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="18442-110">数据类型</span><span class="sxs-lookup"><span data-stu-id="18442-110">Data Type</span></span></p></th>
<th><p><span data-ttu-id="18442-111">说明</span><span class="sxs-lookup"><span data-stu-id="18442-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18442-112">名称</span><span class="sxs-lookup"><span data-stu-id="18442-112">Name</span></span></p></td>
<td><p><span data-ttu-id="18442-113">必需</span><span class="sxs-lookup"><span data-stu-id="18442-113">Required</span></span></p></td>
<td><p><span data-ttu-id="18442-114"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="18442-114"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="18442-p101">一个字符串表达式。请参阅“说明”中的讨论。</span><span class="sxs-lookup"><span data-stu-id="18442-p101">A string expression. See the discussion under Remarks.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18442-117">选项</span><span class="sxs-lookup"><span data-stu-id="18442-117">Options</span></span></p></td>
<td><p><span data-ttu-id="18442-118">可选</span><span class="sxs-lookup"><span data-stu-id="18442-118">Optional</span></span></p></td>
<td><p><span data-ttu-id="18442-119"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="18442-119"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="18442-p102">根据“说明”中的指定设置连接的各个选项。ODBC 驱动程序管理器根据此值向用户提示有关连接的信息，例如数据源名称 (DSN)、用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="18442-p102">sets various options for the connection, as specified in Remarks. Based on this value, the ODBC driver manager prompts the user for connection information such as data source name (DSN), user name, and password.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18442-122">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="18442-122">ReadOnly</span></span></p></td>
<td><p><span data-ttu-id="18442-123">可选</span><span class="sxs-lookup"><span data-stu-id="18442-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="18442-124"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="18442-124"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="18442-125">						如果连接针对只读访问权限打开，则为 <strong>True</strong>；如果连接针对读/写访问权限打开，则为 <strong>False</strong>（默认值）。</span><span class="sxs-lookup"><span data-stu-id="18442-125"><strong>True</strong> if the connection is to be opened for read-only access and <strong>False</strong> if the connection is to be opened for read/write access (default).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18442-126">在浏览器中</span><span class="sxs-lookup"><span data-stu-id="18442-126">Connect</span></span></p></td>
<td><p><span data-ttu-id="18442-127">可选</span><span class="sxs-lookup"><span data-stu-id="18442-127">Optional</span></span></p></td>
<td><p><span data-ttu-id="18442-128"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="18442-128"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="18442-129">将 ODBC 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="18442-129">An ODBC connection string.</span></span> <span data-ttu-id="18442-130">请参阅<strong><a href="connection-connect-property-dao.md">Connect</a></strong>属性为特定的元素和此字符串的语法。</span><span class="sxs-lookup"><span data-stu-id="18442-130">See the <strong><a href="connection-connect-property-dao.md">Connect</a></strong> property for the specific elements and syntax of this string.</span></span> <span data-ttu-id="18442-131">预先计算&quot;ODBC;&quot; ，则需要。</span><span class="sxs-lookup"><span data-stu-id="18442-131">A prepended &quot;ODBC;&quot; is required.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="return-value"></a><span data-ttu-id="18442-132">返回值</span><span class="sxs-lookup"><span data-stu-id="18442-132">Return value</span></span>

<span data-ttu-id="18442-133">Connection</span><span class="sxs-lookup"><span data-stu-id="18442-133">Connection</span></span>

## <a name="remarks"></a><span data-ttu-id="18442-134">注解</span><span class="sxs-lookup"><span data-stu-id="18442-134">Remarks</span></span>

<span data-ttu-id="18442-p104">使用 **OpenConnection** 方法可在 ODBCDirect 工作区中建立与 ODBC 数据源的连接。 **OpenConnection** 方法类似于 **OpenDatabase**，但不完全相同。主要差别在于 **OpenConnection** 只在 ODBCDirect 工作区中可用。</span><span class="sxs-lookup"><span data-stu-id="18442-p104">Use the **OpenConnection** method to establish a connection to an ODBC data source from an ODBCDirect workspace. The **OpenConnection** method is similar but not equivalent to **OpenDatabase**. The main difference is that **OpenConnection** is available only in an ODBCDirect workspace.</span></span>

<span data-ttu-id="18442-138">如果连接参数中指定注册的 ODBC 数据源名称 (DSN)，然后名称参数可以是任何有效的字符串，并将还提供的**Connection**对象的**Name**属性。</span><span class="sxs-lookup"><span data-stu-id="18442-138">If you specify a registered ODBC data source name (DSN) in the connect argument, then the name argument can be any valid string, and will also provide the **Name** property for the **Connection** object.</span></span> <span data-ttu-id="18442-139">如果在连接参数中不包含有效 DSN，名称必须引用有效的 ODBC DSN，还将**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="18442-139">If a valid DSN is not included in the connect argument, then name must refer to a valid ODBC DSN, which will also be the **Name** property.</span></span> <span data-ttu-id="18442-140">如果 name 和连接都不包含有效 DSN，ODBC 驱动程序管理器可以设置 （通过在 options 参数），以提示用户输入所需的连接信息。</span><span class="sxs-lookup"><span data-stu-id="18442-140">If neither name nor connect contains a valid DSN, the ODBC driver manager can be set (via the options argument) to prompt the user for the required connection information.</span></span> <span data-ttu-id="18442-141">然后，通过提示而提供的 DSN 将会提供 **Name** 属性。</span><span class="sxs-lookup"><span data-stu-id="18442-141">The DSN supplied through the prompt then provides the **Name** property.</span></span>

<span data-ttu-id="18442-p106">options 参数确定是否以及何时提示用户建立连接，以及是否异步打开连接。可以使用下列常量之一。</span><span class="sxs-lookup"><span data-stu-id="18442-p106">The options argument determines if and when to prompt the user to establish the connection, and whether or not to open the connection asynchronously. You can use one of the following constants.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="18442-144">常量</span><span class="sxs-lookup"><span data-stu-id="18442-144">Constant</span></span></p></th>
<th><p><span data-ttu-id="18442-145">说明</span><span class="sxs-lookup"><span data-stu-id="18442-145">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18442-146"><strong>dbDriverNoPrompt</strong></span><span class="sxs-lookup"><span data-stu-id="18442-146"><strong>dbDriverNoPrompt</strong></span></span></p></td>
<td><p><span data-ttu-id="18442-p107">ODBC 驱动程序管理器使用 <em>dbname</em> 和 <em>connect</em> 中提供的连接字符串。如果不提供足够的信息，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="18442-p107">The ODBC Driver Manager uses the connection string provided in <em>dbname</em> and <em>connect</em>. If you don't provide sufficient information, a run-time error occurs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18442-149"><strong>dbDriverPrompt</strong></span><span class="sxs-lookup"><span data-stu-id="18442-149"><strong>dbDriverPrompt</strong></span></span></p></td>
<td><p><span data-ttu-id="18442-150">ODBC 驱动程序管理器将显示<strong>ODBC 数据源</strong>对话框，其中显示<em>dbname</em>或<em>连接</em>中的任何提供的相关信息。</span><span class="sxs-lookup"><span data-stu-id="18442-150">The ODBC Driver Manager displays the <strong>ODBC Data Sources</strong> dialog box, which displays any relevant information supplied in <em>dbname</em> or <em>connect</em>.</span></span> <span data-ttu-id="18442-151">连接字符串是组成 DSN 用户选择通过对话框框中，或者，如果用户不指定 dsn 以外，则使用默认 DSN。</span><span class="sxs-lookup"><span data-stu-id="18442-151">The connection string is made up of the DSN that the user selects via the dialog boxes, or, if the user doesn't specify a DSN, the default DSN is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18442-152"><strong>dbDriverComplete</strong></span><span class="sxs-lookup"><span data-stu-id="18442-152"><strong>dbDriverComplete</strong></span></span></p></td>
<td><p><span data-ttu-id="18442-p109">默认值。如果 <em>connect</em> 参数包括完成连接所需的所有必要信息，ODBC 驱动程序管理器将使用 <em>connect</em> 中的字符串。否则，其表现与指定了 <strong>dbDriverPrompt</strong> 时相同。</span><span class="sxs-lookup"><span data-stu-id="18442-p109">Default. If the <em>connect</em> argument includes all the necessary information to complete a connection, the ODBC Driver Manager uses the string in <em>connect</em>. Otherwise it behaves as it does when you specify <strong>dbDriverPrompt</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18442-156"><strong>dbDriverCompleteRequired</strong></span><span class="sxs-lookup"><span data-stu-id="18442-156"><strong>dbDriverCompleteRequired</strong></span></span></p></td>
<td><p><span data-ttu-id="18442-157">此选项的表现类似于 <strong>dbDriverComplete</strong>，不同之处在于，ODBC 驱动程序将禁止提示完成连接所不需要的任何信息。</span><span class="sxs-lookup"><span data-stu-id="18442-157">This option behaves like <strong>dbDriverComplete</strong> except the ODBC driver disables the prompts for any information not required to complete the connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18442-158"><strong>dbRunAsync</strong></span><span class="sxs-lookup"><span data-stu-id="18442-158"><strong>dbRunAsync</strong></span></span></p></td>
<td><p><span data-ttu-id="18442-p110">异步执行方法。此常量可以与其他任何 <em>options</em> 常量一起使用。</span><span class="sxs-lookup"><span data-stu-id="18442-p110">Execute the method asynchronously. This constant may be used with any of the other <em>options</em> constants.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="18442-p111">**OpenConnection** 返回包含有关连接的信息的 **Connection** 对象。 **Connection** 对象与 **[Database](database-object-dao.md)** 对象类似。主要差别在于 **Database** 对象通常代表数据库，尽管也可以使用它代表在 Microsoft Access 工作区中与 ODBC 数据源建立的连接。</span><span class="sxs-lookup"><span data-stu-id="18442-p111">**OpenConnection** returns a **Connection** object which contains information about the connection. The **Connection** object is similar to a **[Database](database-object-dao.md)** object. The principal difference is that a **Database** object usually represents a database, although it can be used to represent a connection to an ODBC data source from a Microsoft Access workspace.</span></span>

