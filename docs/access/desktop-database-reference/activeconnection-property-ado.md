---
<<<<<<< 标头标题： ActiveConnection 属性 (ADO) TOCTitle: ActiveConnection 属性 (ADO) ms:assetid: 5501b2d7-b62c-5fff-1edd-2b7efb3f8c4a ms:mtpsurl: https://msdn.microsoft.com/library/JJ249281(v=office.15) ms:contentKeyID: 48544918 ms.date: 09/18/2015年 ===标题： ActiveConnection 属性 (ADO) TOCTitle: ActiveConnection 属性 (ADO) ms:assetid: 5501b2d7-b62c-5fff-1edd-2b7efb3f8c4a ms:mtpsurl: https://msdn.microsoft.com/library/JJ249281(v=office.15) ms:contentKeyID: 48544918 ms.date: 10/17/2018
>>>>>>> 主 mtps_version: office.15.aspx f1_keywords:
- ado210.chm1231115 f1_categories:
- Office.Version=v15
---

<<<<<<< 标头
# <a name="activeconnection-property-ado"></a>ActiveConnection 属性 (ADO)

=======
# <a name="activeconnection-property-ado"></a>ActiveConnection 属性 (ADO)
>>>>>>> master

**适用于**： Access 2013 |Office 2013

指示指定的 [Command](connection-object-ado.md)、[Recordset](command-object-ado.md) 或 [Record](recordset-object-ado.md) 对象当前属于哪个 [Connection](record-object-ado.md) 对象。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

如果某个连接处于关闭状态，则设置或返回一个 **String** 值，其中包含该连接的定义；如果某个连接处于打开状态，则设置或返回一个 **Variant** ，其中包含当前的 **Connection** 对象。默认值为一个空对象引用。请参阅 [ConnectionString](connectionstring-property-ado.md) 属性。

## <a name="remarks"></a>备注

使用 **ActiveConnection** 属性可以确定 **Connection** 对象，通过该对象将执行指定的 **Command** 对象或打开指定的 **Recordset** 。

<<<<<<< 标头**命令**

对于 **Command** 对象， **ActiveConnection** 属性为读/写属性。

如果在将此属性设置为打开的 [Connection](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) 对象或有效的连接字符串前，尝试对 **Command** 对象调用 **Execute** 方法，则将发生错误。

<a name="microsoft-visual-basicsetting-the-activeconnection-property-to-nothing-disassociates-the-command-object-from-the-current-connection-and-causes-the-provider-to-release-any-associated-resources-on-the-data-source-you-can-then-associate-the-command-object-with-the-same-or-another-connection-object-some-providers-allow-you-to-change-the-property-setting-from-one-connection-to-another-without-having-to-first-set-the-property-to-nothing"></a>**Microsoft Visual Basic**将**ActiveConnection**属性设置为*Nothing*解除关联的**Command**对象从当前的**连接**，并将导致版本上的数据源的任何相关的资源提供程序。 然后可以将 **Command** 对象与同一个或另一个 **Connection** 对象关联。 某些提供程序允许您更改的属性设置从一个**连接**到另一个，而不必先将属性设置为*Nothing*。
=======
### <a name="command"></a>命令

对于 **Command** 对象， **ActiveConnection** 属性为读/写属性。

如果在将此属性设置为打开的 [Connection](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 对象或有效的连接字符串前，尝试对 **Command** 对象调用 **Execute** 方法，则将发生错误。

**Microsoft Visual Basic**： 将**ActiveConnection**属性设置为*Nothing*解除关联从当前**连接**的**Command**对象和导致版本上数据的任何相关的资源提供程序源。 然后可以将 **Command** 对象与同一个或另一个 **Connection** 对象关联。 某些提供程序允许您更改的属性设置从一个**连接**到另一个，而不必先将属性设置为*Nothing*。
>>>>>>> master

如果将**Command**对象的[Parameters](parameters-collection-ado.md)集合包含由提供商的参数，如果您将**ActiveConnection**属性设置为*Nothing*或另一个**Connection**对象清除集合。 如果您手动创建[Parameter](parameter-object-ado.md)对象，并使用它们来填充**Command**对象的**Parameters**集合，设置**ActiveConnection**属性设为*Nothing*或另一个**Connection**对象离开**Parameters**集合保持不变。

如果将与 **Command** 对象关联的 **Connection** 对象关闭，则会将 **ActiveConnection** 属性设置为 *Nothing*。将此属性设置为已关闭的 **Connection** 对象将生成错误。

<<<<<<< 标头**Recordset**
=======
### <a name="recordset"></a>Recordset
>>>>>>> master

对于打开的 **Recordset** 对象或其 **Source** 属性设置为有效 [Command](source-property-ado-recordset.md) 对象的 **Recordset** 对象， **ActiveConnection** 属性为只读属性。否则，该属性为读/写属性。

可以将此属性设置为有效的 **Connection** 对象或有效的连接字符串。在这种情况下，提供程序将使用此定义创建一个新 **Connection** 对象，并打开该连接。此外，提供程序还可能将此属性设置为新 **Connection** 对象，以便提供访问 **Connection** 对象获得扩展错误消息或执行其他命令的方式。

如果您使用[Open](open-method-ado-recordset.md)方法的*ActiveConnection*参数打开**Recordset**对象， **ActiveConnection**属性将继承该参数的值。

如果将 **Recordset** 对象的 **Source** 属性设置为有效的 **Command** 对象变量， **Recordset** 的 **ActiveConnection** 属性将继承 **Command** 对象的 **ActiveConnection** 属性的设置。

<<<<<<< 对象标头**远程数据服务用法**在客户端 Recordset 上使用时，此属性可以设置仅对连接字符串或 （在 Microsoft Visual Basic 或 Visual Basic Scripting Edition） 为*Nothing*。

**Record**

当 **Record** 对象关闭时此属性为可读/写属性，可以包含连接字符串或对打开的 **Connection** 对象的引用。当 **Record** 对象打开时，此属性为只读属性且包含对打开的 **Connection** 对象的引用。

当从 URL 打开 **Record** 对象时，会隐式地创建一个 **Connection** 对象。通过将该 **Connection** 对象分配给此属性，或在 **Open** 方法调用中使用 **Connection** 对象作为参数，可以使用现有的已打开的 **Connection** 对象打开 [Record](open-method-ado-record.md) 。如果 **Record** 是从现有的 **Record** 或 [Recordset](recordset-object-ado.md) 打开的，它将自动与该 **Record** 或 **Recordset** 对象的 **Connection** 对象关联。


> [!NOTE]
> <P>[!注释] 使用 http 方案的 URL 将自动调用 <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>。有关详细信息，请参阅<A href="absolute-and-relative-urls.md">绝对和相对 URL</A>。</P>
=======
**远程数据服务用法**： 当客户端 Recordset 对象上使用，此属性可以仅对连接字符串或设置 （在 Microsoft Visual Basic 或 Visual Basic Scripting Edition） 为*Nothing*。

### <a name="record"></a>Record

当 **Record** 对象关闭时此属性为可读/写属性，可以包含连接字符串或对打开的 **Connection** 对象的引用。当 **Record** 对象打开时，此属性为只读属性且包含对打开的 **Connection** 对象的引用。

当从 URL 打开 **Record** 对象时，会隐式地创建一个 **Connection** 对象。 通过将该 **Connection** 对象分配给此属性，或在 **Open** 方法调用中使用 **Connection** 对象作为参数，可以使用现有的已打开的 **Connection** 对象打开 [Record](open-method-ado-record.md) 。 如果从现有的**Record**或[Recordset](recordset-object-ado.md)打开**Record** ，则自动相关联的**Record**或**Recordset**对象的**Connection**对象。

> [!NOTE]
> [!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。

>>>>>>> master


