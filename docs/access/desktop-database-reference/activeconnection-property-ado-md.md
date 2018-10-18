---
<span data-ttu-id="1cd9a-101"><<<<<<< 标头标题： ActiveConnection 属性 (ADO MD) TOCTitle: ActiveConnection 属性 (ADO MD) ms:assetid: d09f0f91-5e1d-01ed-4d83-eaf58ff718a2 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250043(v=office.15) ms:contentKeyID: 48547845 ms.date: 09/18/2015 mtps_版本： office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="1cd9a-101"><<<<<<< HEAD title: ActiveConnection Property (ADO MD) TOCTitle: ActiveConnection Property (ADO MD) ms:assetid: d09f0f91-5e1d-01ed-4d83-eaf58ff718a2 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250043(v=office.15) ms:contentKeyID: 48547845 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

# <a name="activeconnection-property-ado-md"></a><span data-ttu-id="1cd9a-102">ActiveConnection 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="1cd9a-102">ActiveConnection Property (ADO MD)</span></span>

<span data-ttu-id="1cd9a-103">=== 标题： ActiveConnection 属性 (ADO MD) TOCTitle: ActiveConnection 属性 (ADO MD) ms:assetid: d09f0f91-5e1d-01ed-4d83-eaf58ff718a2 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250043(v=office.15) ms:contentKeyID: 48547845 ms.date: 10/17/2018 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="1cd9a-103">======= title: ActiveConnection property (ADO MD) TOCTitle: ActiveConnection property (ADO MD) ms:assetid: d09f0f91-5e1d-01ed-4d83-eaf58ff718a2 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250043(v=office.15) ms:contentKeyID: 48547845 ms.date: 10/17/2018 mtps_version: v=office.15</span></span>
---

# <a name="activeconnection-property-ado-md"></a><span data-ttu-id="1cd9a-104">ActiveConnection 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="1cd9a-104">ActiveConnection property (ADO MD)</span></span>
>>>>>>> <span data-ttu-id="1cd9a-105">master</span><span class="sxs-lookup"><span data-stu-id="1cd9a-105">master</span></span>

<span data-ttu-id="1cd9a-106">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1cd9a-106">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1cd9a-107">指示当前单元格集或目录当前所属的 ADO [Connection](connection-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-107">Indicates to which ADO [Connection](connection-object-ado.md) object the current cellset or catalog currently belongs.</span></span>

<span data-ttu-id="1cd9a-108"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="1cd9a-108"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="1cd9a-109">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="1cd9a-109">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="1cd9a-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="1cd9a-110">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="1cd9a-111">master</span><span class="sxs-lookup"><span data-stu-id="1cd9a-111">master</span></span>

<span data-ttu-id="1cd9a-p101">设置或返回一个 **Variant** 值，该值包含定义连接的字符串或包含一个 **Connection** 对象。默认值为空。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-p101">Sets or returns a **Variant** that contains a string defining a connection or **Connection** object. The default is empty.</span></span>

## <a name="remarks"></a><span data-ttu-id="1cd9a-114">说明</span><span class="sxs-lookup"><span data-stu-id="1cd9a-114">Remarks</span></span>

<span data-ttu-id="1cd9a-p102">可将此属性设置为有效的 ADO **Connection** 对象，或有效的连接字符串。当此属性设置为连接字符串时，提供程序将使用此定义创建一个新的 **Connection** 对象，并打开该连接。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-p102">You can set this property to a valid ADO **Connection** object or to a valid connection string. When this property is set to a connection string, the provider creates a new **Connection** object using this definition and opens the connection.</span></span>

<span data-ttu-id="1cd9a-117">如果使用 **Open** 方法的 [ActiveConnection](open-method-ado-md.md) 参数打开 [Cellset](cellset-object-ado-md.md) 对象，则 **ActiveConnection** 属性将继承该参数的值。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-117">If you use the **ActiveConnection** argument of the [Open](open-method-ado-md.md) method to open a [Cellset](cellset-object-ado-md.md) object, the **ActiveConnection** property will inherit the value of the argument.</span></span>

<span data-ttu-id="1cd9a-p103">将 **Catalog** 对象的 [ActiveConnection](catalog-object-ado-md.md) 属性设置为 **Nothing** 后，会导致释放关联的数据，包括 [CubeDefs](cubedefs-collection-ado-md.md) 集合以及任何相关的 [Dimension](dimension-object-ado-md.md)、[Hierarchy](hierarchy-object-ado-md.md)、[Level](level-object-ado-md.md) 和 [Member](member-object-ado-md.md) 对象中的数据。关闭用于打开 **Catalog** 的 **Connection** 对象与将 **ActiveConnection** 属性设置为 **Nothing** 的效果相同。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-p103">Setting the **ActiveConnection** property of a [Catalog](catalog-object-ado-md.md) object to **Nothing** releases the associated data, including data in the [CubeDefs](cubedefs-collection-ado-md.md) collection and any related [Dimension](dimension-object-ado-md.md), [Hierarchy](hierarchy-object-ado-md.md), [Level](level-object-ado-md.md), and [Member](member-object-ado-md.md) objects. Closing a **Connection** object that was used to open a **Catalog** has the same effect as setting the **ActiveConnection** property to **Nothing**.</span></span>

<span data-ttu-id="1cd9a-120">更改 **Catalog** 对象的 **ActiveConnection** 属性所引用的连接的默认数据库，会使该 **Catalog** 的内容失效。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-120">Changing the default database of the connection referenced by the **ActiveConnection** property of a **Catalog** object invalidates the contents of the **Catalog**.</span></span>

<span data-ttu-id="1cd9a-121">如果尝试更改打开的 **Cellset** 对象的 **ActiveConnection** 属性，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-121">An error will occur if you attempt to change the **ActiveConnection** property for an open **Cellset** object.</span></span>

<span data-ttu-id="1cd9a-122"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="1cd9a-122"><<<<<<< HEAD</span></span>

> [!NOTE]
> <P><span data-ttu-id="1cd9a-p104">[!注释] 在 Visual Basic 中将 <STRONG>ActiveConnection</STRONG> 属性设置为 <STRONG>Connection</STRONG> 对象时，请不要忘记使用 <STRONG>Set</STRONG> 关键字。如果省略 <STRONG>Set</STRONG> 关键字，您实际上是将 <STRONG>ActiveConnection</STRONG> 属性设置为等于 <STRONG>Connection</STRONG> 对象的默认属性，即 <STRONG>ConnectionString</STRONG> 。代码会运行；但您将创建另一个指向数据源的连接，而这可能会对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-p104">In Visual Basic, remember to use the <STRONG>Set</STRONG> keyword when setting the <STRONG>ActiveConnection</STRONG> property to a <STRONG>Connection</STRONG> object. If you omit the <STRONG>Set</STRONG> keyword, you will actually be setting the <STRONG>ActiveConnection</STRONG> property equal to the <STRONG>Connection</STRONG> object's default property, <STRONG>ConnectionString</STRONG>. The code will work; however, you will create an additional connection to the data source, which may have negative performance implications.</span></span></P>


=======
> [!NOTE]
> <span data-ttu-id="1cd9a-p105">[!注释] 在 Visual Basic 中将 **ActiveConnection** 属性设置为 **Connection** 对象时，请不要忘记使用 **Set** 关键字。如果省略 **Set** 关键字，您实际上是将 **ActiveConnection** 属性设置为等于 **Connection** 对象的默认属性，即 **ConnectionString** 。代码会运行；但您将创建另一个指向数据源的连接，而这可能会对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-p105">In Visual Basic, remember to use the **Set** keyword when setting the **ActiveConnection** property to a **Connection** object. If you omit the **Set** keyword, you will actually be setting the **ActiveConnection** property equal to the **Connection** object's default property, **ConnectionString**. The code will work; however, you will create an additional connection to the data source, which may have negative performance implications.</span></span>
>>>>>>> <span data-ttu-id="1cd9a-129">master</span><span class="sxs-lookup"><span data-stu-id="1cd9a-129">master</span></span>

<span data-ttu-id="1cd9a-p106">使用 MSOLAP 数据提供程序时，请将连接字符串中的数据源设置为服务器名称，将初始目录设置为该数据源中的目录的名称。若要连接到某个与服务器断开的多维数据集文件，请将位置设置为该 .CUB 文件的完整路径。无论在哪种情况下，都应将提供程序设置为提供程序的名称。例如，下面的字符串使用 MSOLAP 提供程序连接到名为 Servername 的服务器上一个名为 Bobs Video Store 的目录：</span><span class="sxs-lookup"><span data-stu-id="1cd9a-p106">When using the MSOLAP data provider, set the data source in a connection string to a server name and set the initial catalog to the name of a catalog from the data source. To connect to a cube file that is disconnected from a server, set the location to the full path to the .CUB file. In either case, set the provider to the provider name. For example, the following string connects to a catalog named Bobs Video Store on a server named Servername with the MSOLAP Provider:</span></span>

`"Data Source=Servername;Initial Catalog=Bobs Video Store;Provider=msolap"`

<span data-ttu-id="1cd9a-134">下面的字符串连接到本地多维数据集文件的位置 c:\\MSDASDK\\示例\\oledb\\olap\\数据\\bobsvid.cub:</span><span class="sxs-lookup"><span data-stu-id="1cd9a-134">The following string connects to a local cube file at the location C:\\MSDASDK\\samples\\oledb\\olap\\data\\bobsvid.cub:</span></span>

`"Location=C:\MSDASDK\samples\oledb\olap\data\bobsvid.cub;Provider=msolap"`

