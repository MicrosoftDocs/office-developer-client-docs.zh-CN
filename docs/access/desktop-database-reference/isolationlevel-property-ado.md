---
<span data-ttu-id="221da-101"><<<<<<< 标头标题： IsolationLevel 属性 (ADO) TOCTitle: IsolationLevel 属性 (ADO) === 标题： IsolationLevel 属性 (ADO) TOCTitle: IsolationLevel 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="221da-101"><<<<<<< HEAD title: IsolationLevel Property (ADO) TOCTitle: IsolationLevel Property (ADO) ======= title: IsolationLevel property (ADO) TOCTitle: IsolationLevel property (ADO)</span></span>
>>>>>>> <span data-ttu-id="221da-102">母版页 ms:assetid: 19461be5-c94b-4b61-ce08-7abdf702c3dc ms:mtpsurl: https://msdn.microsoft.com/library/JJ248939(v=office.15) ms:contentKeyID: 48543493 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="221da-102">master ms:assetid: 19461be5-c94b-4b61-ce08-7abdf702c3dc ms:mtpsurl: https://msdn.microsoft.com/library/JJ248939(v=office.15) ms:contentKeyID: 48543493 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="221da-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="221da-103"><<<<<<< HEAD</span></span>
# <a name="isolationlevel-property-ado"></a><span data-ttu-id="221da-104">IsolationLevel 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="221da-104">IsolationLevel Property (ADO)</span></span>
=======
# <a name="isolationlevel-property-ado"></a><span data-ttu-id="221da-105">IsolationLevel 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="221da-105">IsolationLevel property (ADO)</span></span>
>>>>>>> <span data-ttu-id="221da-106">master</span><span class="sxs-lookup"><span data-stu-id="221da-106">master</span></span>


<span data-ttu-id="221da-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="221da-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="221da-108">指示 [Connection](connection-object-ado.md) 对象的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="221da-108">Indicates the level of isolation for a [Connection](connection-object-ado.md) object.</span></span>

<span data-ttu-id="221da-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="221da-109"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="221da-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="221da-110">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="221da-111">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="221da-111">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="221da-112">master</span><span class="sxs-lookup"><span data-stu-id="221da-112">master</span></span>

<span data-ttu-id="221da-113">设置或返回一个[IsolationLevelEnum](isolationlevelenum.md)值。</span><span class="sxs-lookup"><span data-stu-id="221da-113">Sets or returns an [IsolationLevelEnum](isolationlevelenum.md) value.</span></span> <span data-ttu-id="221da-114">默认值为**adXactChaos**。</span><span class="sxs-lookup"><span data-stu-id="221da-114">The default is **adXactChaos**.</span></span>

## <a name="remarks"></a><span data-ttu-id="221da-115">备注</span><span class="sxs-lookup"><span data-stu-id="221da-115">Remarks</span></span>

<span data-ttu-id="221da-p102">使用 **IsolationLevel** 属性可设置 **Connection** 对象的隔离级别。直到下次调用 [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法时，该设置才会生效。如果请求的隔离级别不可用，则提供程序将返回下一个更高的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="221da-p102">Use the **IsolationLevel** property to set the isolation level of a **Connection** object. The setting does not take effect until the next time you call the [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) method. If the level of isolation you request is unavailable, the provider may return the next greater level of isolation.</span></span>

<span data-ttu-id="221da-119">**IsolationLevel** 属性为可读写状态。</span><span class="sxs-lookup"><span data-stu-id="221da-119">The **IsolationLevel** property is read/write.</span></span>

<span data-ttu-id="221da-120">**远程数据服务用法**当客户端 Connection 对象上使用， **IsolationLevel**属性可以设置仅为**adXactUnspecified**。</span><span class="sxs-lookup"><span data-stu-id="221da-120">**Remote Data Service Usage**When used on a client-side Connection object, the **IsolationLevel** property can be set only to **adXactUnspecified**.</span></span>

<span data-ttu-id="221da-p103">由于用户正在使用客户端缓存上的已断开连接的 **Recordset** 对象，因此可能会出现多用户问题。例如，两个不同的用户试图更新同一条记录时，远程数据服务只允许首先更新该记录的用户实现更新操作。另一个用户的更新请求将失败，并产生错误。</span><span class="sxs-lookup"><span data-stu-id="221da-p103">Because users are working with disconnected **Recordset** objects on a client-side cache, there may be multiuser issues. For instance, when two different users try to update the same record, Remote Data Service simply allows the user who updates the record first to "win." The second user's update request will fail with an error.</span></span>

