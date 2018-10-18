---
<<<<<<< 标头标题： ActiveConnection 属性 (ADO MD) TOCTitle: ActiveConnection 属性 (ADO MD) ms:assetid: d09f0f91-5e1d-01ed-4d83-eaf58ff718a2 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250043(v=office.15) ms:contentKeyID: 48547845 ms.date: 09/18/2015 mtps_版本： office.15.aspx
---

# <a name="activeconnection-property-ado-md"></a>ActiveConnection 属性 (ADO MD)

=== 标题： ActiveConnection 属性 (ADO MD) TOCTitle: ActiveConnection 属性 (ADO MD) ms:assetid: d09f0f91-5e1d-01ed-4d83-eaf58ff718a2 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250043(v=office.15) ms:contentKeyID: 48547845 ms.date: 10/17/2018 mtps_version: office.15.aspx
---

# <a name="activeconnection-property-ado-md"></a>ActiveConnection 属性 (ADO MD)
>>>>>>> master

**适用于**： Access 2013 |Office 2013

指示当前单元格集或目录当前所属的 ADO [Connection](connection-object-ado.md) 对象。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

设置或返回一个 **Variant** 值，该值包含定义连接的字符串或包含一个 **Connection** 对象。默认值为空。

## <a name="remarks"></a>说明

可将此属性设置为有效的 ADO **Connection** 对象，或有效的连接字符串。当此属性设置为连接字符串时，提供程序将使用此定义创建一个新的 **Connection** 对象，并打开该连接。

如果使用 **Open** 方法的 [ActiveConnection](open-method-ado-md.md) 参数打开 [Cellset](cellset-object-ado-md.md) 对象，则 **ActiveConnection** 属性将继承该参数的值。

将 **Catalog** 对象的 [ActiveConnection](catalog-object-ado-md.md) 属性设置为 **Nothing** 后，会导致释放关联的数据，包括 [CubeDefs](cubedefs-collection-ado-md.md) 集合以及任何相关的 [Dimension](dimension-object-ado-md.md)、[Hierarchy](hierarchy-object-ado-md.md)、[Level](level-object-ado-md.md) 和 [Member](member-object-ado-md.md) 对象中的数据。关闭用于打开 **Catalog** 的 **Connection** 对象与将 **ActiveConnection** 属性设置为 **Nothing** 的效果相同。

更改 **Catalog** 对象的 **ActiveConnection** 属性所引用的连接的默认数据库，会使该 **Catalog** 的内容失效。

如果尝试更改打开的 **Cellset** 对象的 **ActiveConnection** 属性，则会发生错误。

<<<<<<< 标头

> [!NOTE]
> <P>[!注释] 在 Visual Basic 中将 <STRONG>ActiveConnection</STRONG> 属性设置为 <STRONG>Connection</STRONG> 对象时，请不要忘记使用 <STRONG>Set</STRONG> 关键字。如果省略 <STRONG>Set</STRONG> 关键字，您实际上是将 <STRONG>ActiveConnection</STRONG> 属性设置为等于 <STRONG>Connection</STRONG> 对象的默认属性，即 <STRONG>ConnectionString</STRONG> 。代码会运行；但您将创建另一个指向数据源的连接，而这可能会对性能产生负面影响。</P>


=======
> [!NOTE]
> [!注释] 在 Visual Basic 中将 **ActiveConnection** 属性设置为 **Connection** 对象时，请不要忘记使用 **Set** 关键字。如果省略 **Set** 关键字，您实际上是将 **ActiveConnection** 属性设置为等于 **Connection** 对象的默认属性，即 **ConnectionString** 。代码会运行；但您将创建另一个指向数据源的连接，而这可能会对性能产生负面影响。
>>>>>>> master

使用 MSOLAP 数据提供程序时，请将连接字符串中的数据源设置为服务器名称，将初始目录设置为该数据源中的目录的名称。若要连接到某个与服务器断开的多维数据集文件，请将位置设置为该 .CUB 文件的完整路径。无论在哪种情况下，都应将提供程序设置为提供程序的名称。例如，下面的字符串使用 MSOLAP 提供程序连接到名为 Servername 的服务器上一个名为 Bobs Video Store 的目录：

`"Data Source=Servername;Initial Catalog=Bobs Video Store;Provider=msolap"`

下面的字符串连接到本地多维数据集文件的位置 c:\\MSDASDK\\示例\\oledb\\olap\\数据\\bobsvid.cub:

`"Location=C:\MSDASDK\samples\oledb\olap\data\bobsvid.cub;Provider=msolap"`

