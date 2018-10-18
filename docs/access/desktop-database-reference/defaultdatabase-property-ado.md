---
<span data-ttu-id="75018-101"><<<<<<< 标头标题： DefaultDatabase 属性 (ADO) TOCTitle: DefaultDatabase 属性 (ADO) === 标题： DefaultDatabase 属性 (ADO) TOCTitle: DefaultDatabase 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="75018-101"><<<<<<< HEAD title: DefaultDatabase Property (ADO) TOCTitle: DefaultDatabase Property (ADO) ======= title: DefaultDatabase property (ADO) TOCTitle: DefaultDatabase property (ADO)</span></span>
>>>>>>> <span data-ttu-id="75018-102">母版页 ms:assetid: a35c5631-f9d9-e51f-950b-e52169830d94 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249757(v=office.15) ms:contentKeyID: 48546784 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="75018-102">master ms:assetid: a35c5631-f9d9-e51f-950b-e52169830d94 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249757(v=office.15) ms:contentKeyID: 48546784 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="75018-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="75018-103"><<<<<<< HEAD</span></span>
# <a name="defaultdatabase-property-ado"></a><span data-ttu-id="75018-104">DefaultDatabase 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="75018-104">DefaultDatabase Property (ADO)</span></span>
=======
# <a name="defaultdatabase-property-ado"></a><span data-ttu-id="75018-105">DefaultDatabase 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="75018-105">DefaultDatabase property (ADO)</span></span>
>>>>>>> <span data-ttu-id="75018-106">master</span><span class="sxs-lookup"><span data-stu-id="75018-106">master</span></span>


<span data-ttu-id="75018-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="75018-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="75018-108">指示 [Connection](connection-object-ado.md) 对象的默认数据库。</span><span class="sxs-lookup"><span data-stu-id="75018-108">Indicates the default database for a [Connection](connection-object-ado.md) object.</span></span>

<span data-ttu-id="75018-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="75018-109"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="75018-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="75018-110">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="75018-111">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="75018-111">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="75018-112">master</span><span class="sxs-lookup"><span data-stu-id="75018-112">master</span></span>

<span data-ttu-id="75018-113">设置或返回一个 **String** 值，该值可计算为提供程序中可用的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="75018-113">Sets or returns a **String** value that evaluates to the name of a database available from the provider.</span></span>

## <a name="remarks"></a><span data-ttu-id="75018-114">备注</span><span class="sxs-lookup"><span data-stu-id="75018-114">Remarks</span></span>

<span data-ttu-id="75018-115">使用 **DefaultDatabase** 属性可以设置或返回特定 **Connection** 对象上的默认数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="75018-115">Use the **DefaultDatabase** property to set or return the name of the default database on a specific **Connection** object.</span></span>

<span data-ttu-id="75018-p101">如果有默认数据库，SQL 字符串可以使用非限定性语法访问该数据库中的对象。若要访问 **DefaultDatabase** 属性中指定的数据库之外的其他数据库中的对象，必须使用所需的数据库名称来限定对象名称。进行连接时，提供程序会将默认数据库信息写入 **DefaultDatabase** 属性中。某些提供程序仅允许一个连接使用一个数据库，在这种情况下就不能更改 **DefaultDatabase** 属性。</span><span class="sxs-lookup"><span data-stu-id="75018-p101">If there is a default database, SQL strings may use an unqualified syntax to access objects in that database. To access objects in a database other than the one specified in the **DefaultDatabase** property, you must qualify object names with the desired database name. Upon connection, the provider will write default database information to the **DefaultDatabase** property. Some providers allow only one database per connection, in which case you cannot change the **DefaultDatabase** property.</span></span>

<span data-ttu-id="75018-120">某些数据源和提供程序可能不支持此功能，会返回错误或空字符串。</span><span class="sxs-lookup"><span data-stu-id="75018-120">Some data sources and providers may not support this feature, and may return an error or an empty string.</span></span>

<span data-ttu-id="75018-121">**远程数据服务用法**此属性不是在客户端**Connection**对象上可用。</span><span class="sxs-lookup"><span data-stu-id="75018-121">**Remote Data Service Usage**This property is not available on a client-side **Connection** object.</span></span>

