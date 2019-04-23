---
title: ActiveConnection 属性 (ADO MD)
TOCTitle: ActiveConnection property (ADO MD)
ms:assetid: d09f0f91-5e1d-01ed-4d83-eaf58ff718a2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250043(v=office.15)
ms:contentKeyID: 48547845
ms.date: 10/17/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 372dac11500647af75881ae6b4aee22a391a32c9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280527"
---
# <a name="activeconnection-property-ado-md"></a><span data-ttu-id="13d31-102">ActiveConnection 属性 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="13d31-102">ActiveConnection property (ADO MD)</span></span>

<span data-ttu-id="13d31-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="13d31-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="13d31-104">指示当前单元格集或目录当前所属的 ADO [Connection](connection-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="13d31-104">Indicates to which ADO [Connection](connection-object-ado.md) object the current cellset or catalog currently belongs.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="13d31-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="13d31-105">Settings and return values</span></span>

<span data-ttu-id="13d31-106">设置或返回一个 **Variant** 值，该值包含定义连接的字符串或包含一个 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="13d31-106">Sets or returns a **Variant** that contains a string defining a connection or **Connection** object.</span></span> <span data-ttu-id="13d31-107">默认值为空。</span><span class="sxs-lookup"><span data-stu-id="13d31-107">The default is empty.</span></span>

## <a name="remarks"></a><span data-ttu-id="13d31-108">注解</span><span class="sxs-lookup"><span data-stu-id="13d31-108">Remarks</span></span>

<span data-ttu-id="13d31-p102">可将此属性设置为有效的 ADO **Connection** 对象，或有效的连接字符串。当此属性设置为连接字符串时，提供程序将使用此定义创建一个新的 **Connection** 对象，并打开该连接。</span><span class="sxs-lookup"><span data-stu-id="13d31-p102">You can set this property to a valid ADO **Connection** object or to a valid connection string. When this property is set to a connection string, the provider creates a new **Connection** object using this definition and opens the connection.</span></span>

<span data-ttu-id="13d31-111">如果使用 **Open** 方法的 [ActiveConnection](open-method-ado-md.md) 参数打开 [Cellset](cellset-object-ado-md.md) 对象，则 **ActiveConnection** 属性将继承该参数的值。</span><span class="sxs-lookup"><span data-stu-id="13d31-111">If you use the **ActiveConnection** argument of the [Open](open-method-ado-md.md) method to open a [Cellset](cellset-object-ado-md.md) object, the **ActiveConnection** property will inherit the value of the argument.</span></span>

<span data-ttu-id="13d31-p103">将 **Catalog** 对象的 [ActiveConnection](catalog-object-ado-md.md) 属性设置为 **Nothing** 后，会导致释放关联的数据，包括 [CubeDefs](cubedefs-collection-ado-md.md) 集合以及任何相关的 [Dimension](dimension-object-ado-md.md)、[Hierarchy](hierarchy-object-ado-md.md)、[Level](level-object-ado-md.md) 和 [Member](member-object-ado-md.md) 对象中的数据。关闭用于打开 **Catalog** 的 **Connection** 对象与将 **ActiveConnection** 属性设置为 **Nothing** 的效果相同。</span><span class="sxs-lookup"><span data-stu-id="13d31-p103">Setting the **ActiveConnection** property of a [Catalog](catalog-object-ado-md.md) object to **Nothing** releases the associated data, including data in the [CubeDefs](cubedefs-collection-ado-md.md) collection and any related [Dimension](dimension-object-ado-md.md), [Hierarchy](hierarchy-object-ado-md.md), [Level](level-object-ado-md.md), and [Member](member-object-ado-md.md) objects. Closing a **Connection** object that was used to open a **Catalog** has the same effect as setting the **ActiveConnection** property to **Nothing**.</span></span>

<span data-ttu-id="13d31-114">更改 **Catalog** 对象的 **ActiveConnection** 属性所引用的连接的默认数据库，会使该 **Catalog** 的内容失效。</span><span class="sxs-lookup"><span data-stu-id="13d31-114">Changing the default database of the connection referenced by the **ActiveConnection** property of a **Catalog** object invalidates the contents of the **Catalog**.</span></span>

<span data-ttu-id="13d31-115">如果尝试更改打开的 **Cellset** 对象的 **ActiveConnection** 属性，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="13d31-115">An error will occur if you attempt to change the **ActiveConnection** property for an open **Cellset** object.</span></span>

> [!NOTE]
> <span data-ttu-id="13d31-p104">[!注释] 在 Visual Basic 中将 **ActiveConnection** 属性设置为 **Connection** 对象时，请不要忘记使用 **Set** 关键字。如果省略 **Set** 关键字，您实际上是将 **ActiveConnection** 属性设置为等于 **Connection** 对象的默认属性，即 **ConnectionString** 。代码会运行；但您将创建另一个指向数据源的连接，而这可能会对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="13d31-p104">In Visual Basic, remember to use the **Set** keyword when setting the **ActiveConnection** property to a **Connection** object. If you omit the **Set** keyword, you will actually be setting the **ActiveConnection** property equal to the **Connection** object's default property, **ConnectionString**. The code will work; however, you will create an additional connection to the data source, which may have negative performance implications.</span></span>

<span data-ttu-id="13d31-p105">使用 MSOLAP 数据提供程序时，请将连接字符串中的数据源设置为服务器名称，将初始目录设置为该数据源中的目录的名称。若要连接到某个与服务器断开的多维数据集文件，请将位置设置为该 .CUB 文件的完整路径。无论在哪种情况下，都应将提供程序设置为提供程序的名称。例如，下面的字符串使用 MSOLAP 提供程序连接到名为 Servername 的服务器上一个名为 Bobs Video Store 的目录：</span><span class="sxs-lookup"><span data-stu-id="13d31-p105">When using the MSOLAP data provider, set the data source in a connection string to a server name and set the initial catalog to the name of a catalog from the data source. To connect to a cube file that is disconnected from a server, set the location to the full path to the .CUB file. In either case, set the provider to the provider name. For example, the following string connects to a catalog named Bobs Video Store on a server named Servername with the MSOLAP Provider:</span></span>

`"Data Source=Servername;Initial Catalog=Bobs Video Store;Provider=msolap"`

<span data-ttu-id="13d31-123">下面的字符串连接到位于 C\\: MSDASDK\\示例\\oledb\\olap\\数据 bobsvid 的本地多维数据\\集文件。 .cub:</span><span class="sxs-lookup"><span data-stu-id="13d31-123">The following string connects to a local cube file at the location C:\\MSDASDK\\samples\\oledb\\olap\\data\\bobsvid.cub:</span></span>

`"Location=C:\MSDASDK\samples\oledb\olap\data\bobsvid.cub;Provider=msolap"`

