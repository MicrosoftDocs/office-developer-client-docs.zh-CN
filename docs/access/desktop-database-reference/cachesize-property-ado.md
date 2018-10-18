---
<span data-ttu-id="d7f1b-101"><<<<<<< 标头标题： CacheSize 属性 (ADO) TOCTitle: CacheSize 属性 (ADO) === 标题： CacheSize 属性 (ADO) TOCTitle: CacheSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="d7f1b-101"><<<<<<< HEAD title: CacheSize Property (ADO) TOCTitle: CacheSize Property (ADO) ======= title: CacheSize property (ADO) TOCTitle: CacheSize property (ADO)</span></span>
>>>>>>> <span data-ttu-id="d7f1b-102">母版页 ms:assetid: 42f86cc0-30dc-669b-9e65-5e7ecd52c4d7 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249200(v=office.15) ms:contentKeyID: 48544491 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="d7f1b-102">master ms:assetid: 42f86cc0-30dc-669b-9e65-5e7ecd52c4d7 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249200(v=office.15) ms:contentKeyID: 48544491 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="d7f1b-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="d7f1b-103"><<<<<<< HEAD</span></span>
# <a name="cachesize-property-ado"></a><span data-ttu-id="d7f1b-104">CacheSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="d7f1b-104">CacheSize Property (ADO)</span></span>
=======
# <a name="cachesize-property-ado"></a><span data-ttu-id="d7f1b-105">CacheSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="d7f1b-105">CacheSize property (ADO)</span></span>
>>>>>>> <span data-ttu-id="d7f1b-106">master</span><span class="sxs-lookup"><span data-stu-id="d7f1b-106">master</span></span>


<span data-ttu-id="d7f1b-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d7f1b-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d7f1b-108">指示本地缓存在内存中的 [Recordset](recordset-object-ado.md) 对象的记录数。</span><span class="sxs-lookup"><span data-stu-id="d7f1b-108">Indicates the number of records from a [Recordset](recordset-object-ado.md) object that are cached locally in memory.</span></span>

<span data-ttu-id="d7f1b-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="d7f1b-109"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="d7f1b-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="d7f1b-110">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="d7f1b-111">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="d7f1b-111">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="d7f1b-112">master</span><span class="sxs-lookup"><span data-stu-id="d7f1b-112">master</span></span>

<span data-ttu-id="d7f1b-p101">设置或返回一个必须大于 0 的 **Long** 值。默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="d7f1b-p101">Sets or returns a **Long** value that must be greater than 0. Default is 1.</span></span>

## <a name="remarks"></a><span data-ttu-id="d7f1b-115">备注</span><span class="sxs-lookup"><span data-stu-id="d7f1b-115">Remarks</span></span>

<span data-ttu-id="d7f1b-p102">使用 **CacheSize** 属性可以控制一次从提供程序检索到本地内存中的记录数。例如，如果 **CacheSize** 为 10，则在首次打开 **Recordset** 对象后，提供程序会将前 10 条记录检索到本地内存中。在 **Recordset** 对象中移动时，提供程序将从本地内存缓冲区中返回数据。在通过缓存中的最后一条记录后，提供程序将立即从数据源中将接下来的 10 条记录检索到缓存中。</span><span class="sxs-lookup"><span data-stu-id="d7f1b-p102">Use the **CacheSize** property to control how many records to retrieve at one time into local memory from the provider. For example, if the **CacheSize** is 10, after first opening the **Recordset** object, the provider retrieves the first 10 records into local memory. As you move through the **Recordset** object, the provider returns the data from the local memory buffer. As soon as you move past the last record in the cache, the provider retrieves the next 10 records from the data source into the cache.</span></span>


> [!NOTE]
> <P><span data-ttu-id="d7f1b-p103">[!注释] <STRONG>CacheSize</STRONG> 基于提供程序特定的属性 <STRONG>Maximum Open Rows</STRONG> （在 <STRONG>Recordset</STRONG> 对象的 <STRONG>Properties</STRONG> 集合中）。不能将 <STRONG>CacheSize</STRONG> 设置为大于 <STRONG>Maximum Open Rows</STRONG> 的值。若要修改提供程序可以打开的行数，请设置 <STRONG>Maximum Open Rows</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="d7f1b-p103"><STRONG>CacheSize</STRONG> is based on the <STRONG>Maximum Open Rows</STRONG> provider-specific property (in the <STRONG>Properties</STRONG> collection of the <STRONG>Recordset</STRONG> object). You cannot set <STRONG>CacheSize</STRONG> to a value greater than <STRONG>Maximum Open Rows</STRONG>. To modify the number of rows which can be opened by the provider, set <STRONG>Maximum Open Rows</STRONG>.</span></span></P>



<span data-ttu-id="d7f1b-p104">**CacheSize** 的值可以在 **Recordset** 对象生存期间进行调整，但更改此值将仅影响在随后对数据源进行检索后缓存中的记录数。仅更此属性值不会更改缓存中的当前内容。</span><span class="sxs-lookup"><span data-stu-id="d7f1b-p104">The value of **CacheSize** can be adjusted during the life of the **Recordset** object, but changing this value only affects the number of records in the cache after subsequent retrievals from the data source. Changing the property value alone will not change the current contents of the cache.</span></span>

<span data-ttu-id="d7f1b-125">如果要检索的记录数小于 **CacheSize** 指定的值，提供程序将返回剩下的记录，而不会发生错误。</span><span class="sxs-lookup"><span data-stu-id="d7f1b-125">If there are fewer records to retrieve than **CacheSize** specifies, the provider returns the remaining records and no error occurs.</span></span>

<span data-ttu-id="d7f1b-126">不允许将 **CacheSize** 设置为零，因为这会返回错误。</span><span class="sxs-lookup"><span data-stu-id="d7f1b-126">A **CacheSize** setting of zero is not allowed and returns an error.</span></span>

<span data-ttu-id="d7f1b-p105">从缓存中检索的记录并不能反映其他用户对数据源所做的并发更改。若要强制更新所有已缓存的数据，请使用 [Resync](resync-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="d7f1b-p105">Records retrieved from the cache don't reflect concurrent changes that other users made to the source data. To force an update of all the cached data, use the [Resync](resync-method-ado.md) method.</span></span>

<span data-ttu-id="d7f1b-p106">如果 **CacheSize** 设置为大于 1  的值，并且在检索了记录后进行了删除操作，导航方法（[Move](move-method-ado.md)、[MoveFirst、MoveLast、MoveNext 和 MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)）可能会导致导航到已经删除的记录。进行了初始提取后，除非尝试访问已删除行中的数据，否则提取后发生的删除不会在数据缓存中得到反映。不过，将 **CacheSize** 设置为 1 就可以解决此问题，因为无法提取已删除的行。</span><span class="sxs-lookup"><span data-stu-id="d7f1b-p106">If **CacheSize** is set to a value greater than one, the navigation methods ([Move](move-method-ado.md), [MoveFirst, MoveLast, MoveNext, and MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)) may result in navigation to a deleted record, if deletion occurs after the records were retrieved. After the initial fetch, subsequent deletions will not be reflected in your data cache until you attempt to access a data value from a deleted row. However, setting **CacheSize** to one eliminates this issue since deleted rows cannot be fetched.</span></span>

