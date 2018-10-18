---
<<<<<<< 标头标题： 绝对和相对 Url TOCTitle： 绝对和相对 Url ms:assetid: 79a1f793-7154-1c13-7dfe-a1b8cd64e1ea ms:mtpsurl: https://msdn.microsoft.com/library/JJ249501(v=office.15) ms:contentKeyID: 48545774 ms.date: 09/18/2015 mtps_version: v =office.15
---

# <a name="absolute-and-relative-urls"></a>绝对 URL 和相对 URL

**适用于**： Access 2013 |Office 2013 

<a name="a-url-specifies-the-location-of-a-target-stored-on-a-local-or-networked-computer-such-as-a-file-directory-html-page-image-program-and-so-on-in-this-discussion-an-absolute-url-is-of-the-form"></a>URL 指定存储的本地或网络的计算机，如文件、 目录、 HTML 页、 图像、 程序和等等 *。* 上的目标的位置 在此次讨论中，*绝对 URL*的形式：
=======
标题： 绝对和相对 Url TOCTitle： 绝对和相对 Url ms:assetid: 79a1f793-7154-1c13-7dfe-a1b8cd64e1ea ms:mtpsurl: https://msdn.microsoft.com/library/JJ249501(v=office.15) ms:contentKeyID: 48545774 ms.date: 10/17/2018 mtps_version: office.15.aspx
---

# <a name="absolute-and-relative-urls"></a>绝对和相对 Url

**适用于**： Access 2013 |Office 2013 

URL 指定在本地或网络计算机上存储的目标（如文件、目录、HTML 页、图像、程序等）的位置。 在此次讨论中，*绝对 URL*的形式：
>>>>>>> master

*scheme://server/path/resource*

其中：

<<<<<<< 标头
  - *scheme*

  - 指定如何访问*资源*。

  - *server*

  - 指定*资源*所在的计算机的名称。

  - *path*

  - 指定在目标前面的目录序列。如果省略 *resource*，则目标是 *path* 中最后一个目录。

  - *resource*

  - 如果包含，*资源*是目标，并且通常是文件的名称。 它可能包含单个二进制字节流或包含一个或多个存储和二进制字节流的*结构化的文档*的*简单文件*。
=======
|名称 |说明|
|:----|:----------|
|*scheme*|指定如何访问*资源*。|
|*server*|指定*资源*所在的计算机的名称。|
|*path*|指定在目标前面的目录序列。如果省略 *resource*，则目标是 *path* 中最后一个目录。|
|*resource*|如果包含，*资源*是目标，并且通常是文件的名称。 它可能是*简单文件*，包含单个的字节数或*结构化的文档*，其中包含一个或多个存储和二进制字节流的二进制流。|
>>>>>>> master

*绝对 URL*包含定位资源所需的所有信息。

*相对 URL* 使用绝对 URL 作为起点来定位资源。实际上，目标的“完整 URL”是通过将绝对和相对 URL 连接在一起指定的。相对 URL 通常只由 *path* 和可选的 *resource* 组成，但没有 *scheme* 或 *server*。

<<<<<<< 标头
## <a name="url-scheme-registration"></a>URL 架构注册

如果提供程序支持 URL，它将注册一个或多个 URL 架构。 这意味着使用此架构的任何 URL 都将自动调用所注册的提供程序。 例如， *http*方案被注册到[Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 ADO 假定前缀为"http"的所有 URL 都表示要使用 Internet Publishing Provider 的 Web 文件夹或文件。 有关由提供程序注册的架构的信息，请参阅提供程序文档。

## <a name="defining-context-with-a-url"></a>使用 URL 定义上下文
=======
## <a name="url-scheme-registration"></a>URL 架构注册

如果提供程序支持 URL，它将注册一个或多个 URL 架构。 这意味着使用此架构的任何 URL 都将自动调用所注册的提供程序。 例如， *http*方案被注册到[Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 ADO 假定带有"http"前缀的所有 Url 都表示 web 文件夹或文件与 Internet Publishing Provider 一起使用。 有关由提供程序注册的架构的信息，请参阅提供程序文档。

## <a name="defining-context-with-a-url"></a>使用 URL 定义上下文
>>>>>>> master

打开的连接（由 [Connection](connection-object-ado.md) 对象表示）的一个功能是将随后的操作限制到由该连接表示的数据源。就是说，连接定义了后续操作的上下文。

使用 ADO 2.5，绝对 URL 也可能定义上下文。例如，使用绝对 URL 打开 [Record](record-object-ado.md) 对象时，将隐式创建 **Connection** 对象以表示该 URL 所指定的资源。

<<<<<<< 标头可能**记录**的*ActiveConnection*参数中指定的绝对 URL 定义上下文对象的[Open](open-method-ado-record.md)方法。 绝对 URL 也可指定为的新值"URL**=**"**连接**对象[Open](open-method-ado-connection.md)方法*ConnectionString*参数和[Open](open-method-ado-recordset.md)方法*ActiveConnection 的[Recordset](recordset-object-ado.md)对象中的关键字*参数。

还可以用表示目录的已打开 **Record** 或 **Recordset** 对象来定义上下文，因为这些对象已经具有用于指定上下文的隐式或显式声明的 **Connection** 对象。

## <a name="scoped-operations"></a>确定了范围的操作

上下文同时定义*范围*— 即，目录和可能参与后续操作其子目录。 **Record** 对象具有多个对目录及其所有子目录操作的已确定范围的方法，包括 [CopyRecord](copyrecord-method-ado.md)、[MoveRecord](moverecord-method-ado.md) 和 [DeleteRecord](https://msdn.microsoft.com/library/jj249832\(v=office.15\))。

## <a name="relative-urls-as-command-text"></a>作为命令文本的相对 URL
=== 定义上下文的绝对 URL 可能**Record**对象的[Open](open-method-ado-record.md)方法的*ActiveConnection*参数中指定。 绝对 URL 也可指定为的新值`URL=`**连接**对象[Open](open-method-ado-connection.md)方法*ConnectionString*参数和[Open](open-method-ado-recordset.md)方法的*ActiveConnection*的[Recordset](recordset-object-ado.md)对象中的关键字参数。

还可以用表示目录的已打开 **Record** 或 **Recordset** 对象来定义上下文，因为这些对象已经具有用于指定上下文的隐式或显式声明的 **Connection** 对象。

## <a name="scoped-operations"></a>范围的操作

上下文同时定义*范围*— 即，目录和可能参与后续操作其子目录。 **Record** 对象具有多个对目录及其所有子目录操作的已确定范围的方法，包括 [CopyRecord](copyrecord-method-ado.md)、[MoveRecord](moverecord-method-ado.md) 和 [DeleteRecord](deleterecord-method-ado.md)。

## <a name="relative-urls-as-command-text"></a>作为命令文本的相对 Url
>>>>>>> master

**Connection**对象**执行**方法*CommandText*参数，和**Recordset**对象的**Open**方法*Source*参数可以指定一个字符串，指定数据源上执行的命令。

可能*CommandText*或*源*参数中指定的相对 URL。 相对 URL 实际上不指定命令（如 SQL 命令）；命令是在那些参数中指定的。 此外，活动连接的上下文必须是绝对 URL，并且*选项*参数必须设置为**adCmdTableDirect**。

例如，可以对 Winnt/system32 目录的 Readme25.txt 文件打开 **Recordset** ，如下所示：

```vb
recordset.Open "system32/Readme25.txt", "URL=https://YourServer/Winnt/",,,adCmdTableDirect 
```

<<<<<<< HEAD 连接字符串中的绝对 URL 指定的服务器 (YourServer) 的路径 （） 和 （可以对） 的路径。 此 URL 还定义了上下文。

命令文本中的相对 URL 使用绝对 URL 作为起点，并指定的路径 (system32) 和要打开 （） 的文件和文件以打开 (Readme25.txt) 的其余部分。

<a name="the-options-field--indicates-that-the-command-type-is-a-relative-url"></a>选项字段 () 指示命令类型是一个相对 URL。
=======
连接字符串中的绝对 URL 指定的服务器 (YourServer) 和 （可以对） 的路径。 此 URL 还定义了上下文。

命令文本中的相对 URL 使用绝对 URL 作为起点，并指定的路径 (system32) 和要打开 (Readme25.txt) 的文件的其余部分。

选项字段指示命令类型是相对 URL。
>>>>>>> master

作为另一个示例，以下代码将在目录的内容中打开一个 **Recordset** ：

```vb
recordset.Open "", "URL=https://YourServer/Winnt/",,,adCmdTableDirect 
```

<<<<<<< 标头
## <a name="ole-db-provider-supplied-url-schemes"></a>OLE DB 提供程序提供的 URL 架构

完全限定的 URL 的前导部分是用来访问标识由 URL 的其余部分的资源的*方案*。 示例是 HTTP （超文本传输协议） 和 FTP （文件传输协议）。

<a name="ado-supports-ole-db-providers-that-recognize-their-own-url-schemes-for-example-the-microsoft-ole-db-provider-for-internet-publishingmicrosoft-ole-db-provider-for-internet-publishingmd-which-accesses-published-windows-2000-files-recognizes-the-existing-http-scheme"></a>ADO 支持识别自己 URL 方案的 OLE DB 提供程序。 例如， [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)*，* 哪些访问"发布"Windows 2000 文件，识别现有的 HTTP 架构。
=======
## <a name="ole-db-provider-supplied-url-schemes"></a>OLE DB 提供程序提供的 URL 架构

完全限定的 URL 的前导部分是用来访问标识由 URL 的其余部分的资源的*方案*。 示例是 HTTP （超文本传输协议） 和 FTP （文件传输协议）。

ADO 支持识别自己 URL 方案的 OLE DB 提供程序。 例如， [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)，哪些访问"发布"Windows 2000 文件，识别现有的 HTTP 架构。
>>>>>>> master

