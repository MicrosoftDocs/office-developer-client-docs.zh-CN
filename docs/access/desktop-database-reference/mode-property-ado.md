---
<span data-ttu-id="7872f-101"><<<<<<< 标头标题： 模式属性 (ADO) TOCTitle： 模式属性 (ADO) === 标题： Mode 属性 (ADO) TOCTitle: Mode 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="7872f-101"><<<<<<< HEAD title: Mode Property (ADO) TOCTitle: Mode Property (ADO) ======= title: Mode property (ADO) TOCTitle: Mode property (ADO)</span></span>
>>>>>>> <span data-ttu-id="7872f-102">母版页 ms:assetid: 62086f4f-8624-16c4-dae1-a17475d1864d ms:mtpsurl: https://msdn.microsoft.com/library/JJ249365(v=office.15) ms:contentKeyID: 48545227 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="7872f-102">master ms:assetid: 62086f4f-8624-16c4-dae1-a17475d1864d ms:mtpsurl: https://msdn.microsoft.com/library/JJ249365(v=office.15) ms:contentKeyID: 48545227 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="7872f-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="7872f-103"><<<<<<< HEAD</span></span>
# <a name="mode-property-ado"></a><span data-ttu-id="7872f-104">Mode 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="7872f-104">Mode Property (ADO)</span></span>
=======
# <a name="mode-property-ado"></a><span data-ttu-id="7872f-105">Mode 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="7872f-105">Mode property (ADO)</span></span>
>>>>>>> <span data-ttu-id="7872f-106">master</span><span class="sxs-lookup"><span data-stu-id="7872f-106">master</span></span>


<span data-ttu-id="7872f-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="7872f-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="7872f-108">指示在 [Connection](connection-object-ado.md)、[Record](record-object-ado.md) 或 [Stream](stream-object-ado.md) 对象中修改数据的可用权限。</span><span class="sxs-lookup"><span data-stu-id="7872f-108">Indicates the available permissions for modifying data in a [Connection](connection-object-ado.md), [Record](record-object-ado.md), or [Stream](stream-object-ado.md) object.</span></span>

<span data-ttu-id="7872f-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="7872f-109"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="7872f-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="7872f-110">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="7872f-111">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="7872f-111">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="7872f-112">master</span><span class="sxs-lookup"><span data-stu-id="7872f-112">master</span></span>

<span data-ttu-id="7872f-p101">设置或返回一个 [ConnectModeEnum](connectmodeenum.md) 值。**Connection** 的默认值为 **adModeUnknown**。**Record** 对象的默认值为 **adModeRead**。与基础源关联的 **Stream**（通过作为源的 URL 打开，或作为 **Record** 的默认 **Stream** 打开）的默认值为 **adModeRead**。不与基础源关联的 **Stream**（在内存中实例化）的默认值为 **adModeUnknown**。</span><span class="sxs-lookup"><span data-stu-id="7872f-p101">Sets or returns a [ConnectModeEnum](connectmodeenum.md) value. The default value for a **Connection** is **adModeUnknown**. The default value for a **Record** object is **adModeRead**. The default value for a **Stream** associated with an underlying source (opened with a URL as the source, or as the default **Stream** of a **Record**) is **adModeRead**. The default value for a **Stream** not associated with an underlying source (instantiated in memory) is **adModeUnknown**.</span></span>

## <a name="remarks"></a><span data-ttu-id="7872f-118">备注</span><span class="sxs-lookup"><span data-stu-id="7872f-118">Remarks</span></span>

<span data-ttu-id="7872f-p102">使用 **Mode** 属性可设置或返回提供程序在当前连接上使用的访问权限。只有 **Connection** 对象关闭时才可以设置 **Mode** 属性。</span><span class="sxs-lookup"><span data-stu-id="7872f-p102">Use the **Mode** property to set or return the access permissions in use by the provider on the current connection. You can set the **Mode** property only when the **Connection** object is closed.</span></span>

<span data-ttu-id="7872f-p103">对于 **Stream** 对象，如果未指定访问模式，则从用于打开该 **Stream** 对象的源继承。例如，如果从 **Record** 对象打开 **Stream** ，则默认情况下，其打开模式与 **Record** 相同。</span><span class="sxs-lookup"><span data-stu-id="7872f-p103">For a **Stream** object, if the access mode is not specified, it is inherited from the source used to open the **Stream** object. For example, if a **Stream** is opened from a **Record** object, by default it is opened in the same mode as the **Record**.</span></span>

<span data-ttu-id="7872f-123">对象关闭时此属性为可读/写属性，对象打开时为只读属性。</span><span class="sxs-lookup"><span data-stu-id="7872f-123">This property is read/write while the object is closed and read-only while the object is open.</span></span>

<span data-ttu-id="7872f-124">**远程数据服务用法**当客户端 Connection 对象上使用时， **Mode**属性可以仅可设为**adModeUnknown**。</span><span class="sxs-lookup"><span data-stu-id="7872f-124">**Remote Data Service Usage**When used on a client-side Connection object, the **Mode** property can only be set to **adModeUnknown**.</span></span>

