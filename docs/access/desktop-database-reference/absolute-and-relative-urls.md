---
title: 绝对和相对 Url
TOCTitle: Absolute and relative URLs
ms:assetid: 79a1f793-7154-1c13-7dfe-a1b8cd64e1ea
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249501(v=office.15)
ms:contentKeyID: 48545774
ms.date: 10/17/2018
mtps_version: v=office.15
ms.openlocfilehash: 39286a3b94712c15628e6163c12ee7c8d2d3e502
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25882733"
---
# <a name="absolute-and-relative-urls"></a><span data-ttu-id="e87bd-102">绝对和相对 Url</span><span class="sxs-lookup"><span data-stu-id="e87bd-102">Absolute and relative URLs</span></span>

<span data-ttu-id="e87bd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e87bd-103">**Applies to**: Access 2013, Office 2013</span></span>    

<span data-ttu-id="e87bd-104">URL 指定在本地或网络计算机上存储的目标（如文件、目录、HTML 页、图像、程序等）的位置。</span><span class="sxs-lookup"><span data-stu-id="e87bd-104">A URL specifies the location of a target stored on a local or networked computer, such as a file, directory, HTML page, image, program, and so on.</span></span> <span data-ttu-id="e87bd-105">在此次讨论中，*绝对 URL*的形式：</span><span class="sxs-lookup"><span data-stu-id="e87bd-105">In this discussion, an *absolute URL* is of the form:</span></span>

<span data-ttu-id="e87bd-106">*scheme://server/path/resource*</span><span class="sxs-lookup"><span data-stu-id="e87bd-106">*scheme://server/path/resource*</span></span>

<span data-ttu-id="e87bd-107">其中：</span><span class="sxs-lookup"><span data-stu-id="e87bd-107">where:</span></span>

|<span data-ttu-id="e87bd-108">名称</span><span class="sxs-lookup"><span data-stu-id="e87bd-108">Name</span></span> |<span data-ttu-id="e87bd-109">说明</span><span class="sxs-lookup"><span data-stu-id="e87bd-109">Description</span></span>|
|:----|:----------|
|<span data-ttu-id="e87bd-110">*scheme*</span><span class="sxs-lookup"><span data-stu-id="e87bd-110">*scheme*</span></span>|<span data-ttu-id="e87bd-111">指定如何访问*资源*。</span><span class="sxs-lookup"><span data-stu-id="e87bd-111">Specifies how the *resource* is to be accessed.</span></span>|
|<span data-ttu-id="e87bd-112">*server*</span><span class="sxs-lookup"><span data-stu-id="e87bd-112">*server*</span></span>|<span data-ttu-id="e87bd-113">指定*资源*所在的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="e87bd-113">Specifies the name of the computer where the *resource* is located.</span></span>|
|<span data-ttu-id="e87bd-114">*path*</span><span class="sxs-lookup"><span data-stu-id="e87bd-114">*path*</span></span>|<span data-ttu-id="e87bd-p102">指定在目标前面的目录序列。如果省略 *resource*，则目标是 *path* 中最后一个目录。</span><span class="sxs-lookup"><span data-stu-id="e87bd-p102">Specifies the sequence of directories leading to the target. If *resource* is omitted, the target is the last directory in *path*.</span></span>|
|<span data-ttu-id="e87bd-117">*resource*</span><span class="sxs-lookup"><span data-stu-id="e87bd-117">*resource*</span></span>|<span data-ttu-id="e87bd-118">如果包含，*资源*是目标，并且通常是文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e87bd-118">If included, *resource* is the target, and is typically the name of a file.</span></span> <span data-ttu-id="e87bd-119">它可能是*简单文件*，包含单个的字节数或*结构化的文档*，其中包含一个或多个存储和二进制字节流的二进制流。</span><span class="sxs-lookup"><span data-stu-id="e87bd-119">It may be a *simple file*, containing a single binary stream of bytes, or a *structured document*, containing one or more storages and binary streams of bytes.</span></span>|

<span data-ttu-id="e87bd-120">*绝对 URL*包含定位资源所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="e87bd-120">An *absolute URL* contains all the information necessary to locate a resource.</span></span>

<span data-ttu-id="e87bd-p104">*相对 URL* 使用绝对 URL 作为起点来定位资源。实际上，目标的“完整 URL”是通过将绝对和相对 URL 连接在一起指定的。相对 URL 通常只由 *path* 和可选的 *resource* 组成，但没有 *scheme* 或 *server*。</span><span class="sxs-lookup"><span data-stu-id="e87bd-p104">A *relative URL* locates a resource using an absolute URL as a starting point. In effect, the "complete URL" of the target is specified by concatenating the absolute and relative URLs. A relative URL typically consists only of the *path*, and optionally, the *resource*, but no *scheme* or *server*.</span></span>

## <a name="url-scheme-registration"></a><span data-ttu-id="e87bd-124">URL 架构注册</span><span class="sxs-lookup"><span data-stu-id="e87bd-124">URL scheme registration</span></span>

<span data-ttu-id="e87bd-125">如果提供程序支持 URL，它将注册一个或多个 URL 架构。</span><span class="sxs-lookup"><span data-stu-id="e87bd-125">If a provider supports URLs, it will register for one or more URL schemes.</span></span> <span data-ttu-id="e87bd-126">这意味着使用此架构的任何 URL 都将自动调用所注册的提供程序。</span><span class="sxs-lookup"><span data-stu-id="e87bd-126">This means that any URLs using this scheme will automatically invoke the registered provider.</span></span> <span data-ttu-id="e87bd-127">例如， *http*方案被注册到[Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="e87bd-127">For example, the *http* scheme is registered to the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md).</span></span> <span data-ttu-id="e87bd-128">ADO 假定带有"http"前缀的所有 Url 都表示 web 文件夹或文件与 Internet Publishing Provider 一起使用。</span><span class="sxs-lookup"><span data-stu-id="e87bd-128">ADO assumes all URLs prefixed with "http" represent web folders or files to be used with the Internet Publishing Provider.</span></span> <span data-ttu-id="e87bd-129">有关由提供程序注册的架构的信息，请参阅提供程序文档。</span><span class="sxs-lookup"><span data-stu-id="e87bd-129">For information about the schemes registered by your provider, see your provider documentation.</span></span>

## <a name="defining-context-with-a-url"></a><span data-ttu-id="e87bd-130">使用 URL 定义上下文</span><span class="sxs-lookup"><span data-stu-id="e87bd-130">Defining context with a URL</span></span>

<span data-ttu-id="e87bd-p106">打开的连接（由 [Connection](connection-object-ado.md) 对象表示）的一个功能是将随后的操作限制到由该连接表示的数据源。就是说，连接定义了后续操作的上下文。</span><span class="sxs-lookup"><span data-stu-id="e87bd-p106">One function of an open connection, represented by a [Connection](connection-object-ado.md) object, is to restrict subsequent operations to the data source represented by that connection. That is, the connection defines the context for subsequent operations.</span></span>

<span data-ttu-id="e87bd-p107">使用 ADO 2.5，绝对 URL 也可能定义上下文。例如，使用绝对 URL 打开 [Record](record-object-ado.md) 对象时，将隐式创建 **Connection** 对象以表示该 URL 所指定的资源。</span><span class="sxs-lookup"><span data-stu-id="e87bd-p107">With ADO 2.5, an absolute URL may also define a context. For example, when a [Record](record-object-ado.md) object is opened with an absolute URL, a **Connection** object is implicitly created to represent the resource specified by the URL.</span></span>

<span data-ttu-id="e87bd-135">定义上下文的绝对 URL 可能**Record**对象的[Open](open-method-ado-record.md)方法的*ActiveConnection*参数中指定。</span><span class="sxs-lookup"><span data-stu-id="e87bd-135">An absolute URL that defines a context may be specified in the *ActiveConnection* parameter of the **Record** object [Open](open-method-ado-record.md) method.</span></span> <span data-ttu-id="e87bd-136">绝对 URL 也可指定为的新值`URL=`**连接**对象[Open](open-method-ado-connection.md)方法*ConnectionString*参数和[Open](open-method-ado-recordset.md)方法的*ActiveConnection*的[Recordset](recordset-object-ado.md)对象中的关键字参数。</span><span class="sxs-lookup"><span data-stu-id="e87bd-136">An absolute URL may also be specified as the value of the new `URL=` keyword in the **Connection** object [Open](open-method-ado-connection.md) method *ConnectionString* parameter, and the [Recordset](recordset-object-ado.md) object [Open](open-method-ado-recordset.md) method *ActiveConnection* parameter.</span></span>

<span data-ttu-id="e87bd-137">还可以用表示目录的已打开 **Record** 或 **Recordset** 对象来定义上下文，因为这些对象已经具有用于指定上下文的隐式或显式声明的 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="e87bd-137">Context may also be defined with an open **Record** or **Recordset** object that represents a directory because these objects already have an implicitly or explicitly declared **Connection** object that specifies context.</span></span>

## <a name="scoped-operations"></a><span data-ttu-id="e87bd-138">范围的操作</span><span class="sxs-lookup"><span data-stu-id="e87bd-138">Scoped operations</span></span>

<span data-ttu-id="e87bd-139">上下文同时定义*范围*— 即，目录和可能参与后续操作其子目录。</span><span class="sxs-lookup"><span data-stu-id="e87bd-139">The context simultaneously defines a *scope*—that is, the directory and its subdirectories that may participate in subsequent operations.</span></span> <span data-ttu-id="e87bd-140">**Record** 对象具有多个对目录及其所有子目录操作的已确定范围的方法，包括 [CopyRecord](copyrecord-method-ado.md)、[MoveRecord](moverecord-method-ado.md) 和 [DeleteRecord](deleterecord-method-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="e87bd-140">The **Record** object has several scoped methods, including [CopyRecord](copyrecord-method-ado.md), [MoveRecord](moverecord-method-ado.md), and [DeleteRecord](deleterecord-method-ado.md), that operate on a directory and all its subdirectories.</span></span>

## <a name="relative-urls-as-command-text"></a><span data-ttu-id="e87bd-141">作为命令文本的相对 Url</span><span class="sxs-lookup"><span data-stu-id="e87bd-141">Relative URLs as command text</span></span>

<span data-ttu-id="e87bd-142">**Connection**对象**执行**方法*CommandText*参数，和**Recordset**对象的**Open**方法*Source*参数可以指定一个字符串，指定数据源上执行的命令。</span><span class="sxs-lookup"><span data-stu-id="e87bd-142">A string specifying a command to be executed on the data source may be specified in the **Connection** object **Execute** method *CommandText* parameter, and the **Recordset** object **Open** method *Source* parameter.</span></span>

<span data-ttu-id="e87bd-143">可能*CommandText*或*源*参数中指定的相对 URL。</span><span class="sxs-lookup"><span data-stu-id="e87bd-143">A relative URL may be specified in the *CommandText* or *Source* parameter.</span></span> <span data-ttu-id="e87bd-144">相对 URL 实际上不指定命令（如 SQL 命令）；命令是在那些参数中指定的。</span><span class="sxs-lookup"><span data-stu-id="e87bd-144">The relative URL does not actually specify a command (such as an SQL command); it is merely specified in those parameters.</span></span> <span data-ttu-id="e87bd-145">此外，活动连接的上下文必须是绝对 URL，并且*选项*参数必须设置为**adCmdTableDirect**。</span><span class="sxs-lookup"><span data-stu-id="e87bd-145">In addition, the context of the active connection must be an absolute URL, and the *Option* parameter must be set to **adCmdTableDirect**.</span></span>

<span data-ttu-id="e87bd-146">例如，可以对 Winnt/system32 目录的 Readme25.txt 文件打开 **Recordset** ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e87bd-146">For example, a **Recordset** could be opened on the Readme25.txt file of the Winnt/system32 directory like this:</span></span>

```vb
recordset.Open "system32/Readme25.txt", "URL=https://YourServer/Winnt/",,,adCmdTableDirect 
```

<span data-ttu-id="e87bd-147">连接字符串中的绝对 URL 指定的服务器 (YourServer) 和 （可以对） 的路径。</span><span class="sxs-lookup"><span data-stu-id="e87bd-147">The absolute URL in the connection string specifies the server (YourServer) and the path (Winnt).</span></span> <span data-ttu-id="e87bd-148">此 URL 还定义了上下文。</span><span class="sxs-lookup"><span data-stu-id="e87bd-148">This URL also defines the context.</span></span>

<span data-ttu-id="e87bd-149">命令文本中的相对 URL 使用绝对 URL 作为起点，并指定的路径 (system32) 和要打开 (Readme25.txt) 的文件的其余部分。</span><span class="sxs-lookup"><span data-stu-id="e87bd-149">The relative URL in the command text uses the absolute URL as a starting point and specifies the remainder of the path (system32) and the file to open (Readme25.txt).</span></span>

<span data-ttu-id="e87bd-150">选项字段指示命令类型是相对 URL。</span><span class="sxs-lookup"><span data-stu-id="e87bd-150">The options field indicates that the command type is a relative URL.</span></span>

<span data-ttu-id="e87bd-151">作为另一个示例，以下代码将在目录的内容中打开一个 **Recordset** ：</span><span class="sxs-lookup"><span data-stu-id="e87bd-151">As another example, the following code will open a **Recordset** on the contents of the directory:</span></span>

```vb
recordset.Open "", "URL=https://YourServer/Winnt/",,,adCmdTableDirect 
```

## <a name="ole-db-provider-supplied-url-schemes"></a><span data-ttu-id="e87bd-152">OLE DB 提供程序提供的 URL 架构</span><span class="sxs-lookup"><span data-stu-id="e87bd-152">OLE DB provider-supplied URL schemes</span></span>

<span data-ttu-id="e87bd-153">完全限定的 URL 的前导部分是用来访问标识由 URL 的其余部分的资源的*方案*。</span><span class="sxs-lookup"><span data-stu-id="e87bd-153">The leading part of a fully-qualified URL is the *scheme* used to access the resource identified by the remainder of the URL.</span></span> <span data-ttu-id="e87bd-154">示例是 HTTP （超文本传输协议） 和 FTP （文件传输协议）。</span><span class="sxs-lookup"><span data-stu-id="e87bd-154">Examples are HTTP (HyperText Transfer Protocol) and FTP (File Transfer Protocol).</span></span>

<span data-ttu-id="e87bd-155">ADO 支持识别自己 URL 方案的 OLE DB 提供程序。</span><span class="sxs-lookup"><span data-stu-id="e87bd-155">ADO supports OLE DB providers that recognize their own URL schemes.</span></span> <span data-ttu-id="e87bd-156">例如， [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)，哪些访问"发布"Windows 2000 文件，识别现有的 HTTP 架构。</span><span class="sxs-lookup"><span data-stu-id="e87bd-156">For example, the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md), which accesses "published" Windows 2000 files, recognizes the existing HTTP scheme.</span></span>

