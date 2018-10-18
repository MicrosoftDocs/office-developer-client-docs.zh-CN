---
<span data-ttu-id="c4d7c-101"><<<<<<< 标头标题： MaxRecords 属性 (ADO) TOCTitle: MaxRecords 属性 (ADO) === 标题： MaxRecords 属性 (ADO) TOCTitle: MaxRecords 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c4d7c-101"><<<<<<< HEAD title: MaxRecords Property (ADO) TOCTitle: MaxRecords Property (ADO) ======= title: MaxRecords property (ADO) TOCTitle: MaxRecords property (ADO)</span></span>
>>>>>>> <span data-ttu-id="c4d7c-102">母版页 ms:assetid: 424b2d41-073a-3fbe-30aa-99fac94f9a81 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249195(v=office.15) ms:contentKeyID: 48544475 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="c4d7c-102">master ms:assetid: 424b2d41-073a-3fbe-30aa-99fac94f9a81 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249195(v=office.15) ms:contentKeyID: 48544475 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="c4d7c-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="c4d7c-103"><<<<<<< HEAD</span></span>
# <a name="maxrecords-property-ado"></a><span data-ttu-id="c4d7c-104">MaxRecords 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c4d7c-104">MaxRecords Property (ADO)</span></span>
=======
# <a name="maxrecords-property-ado"></a><span data-ttu-id="c4d7c-105">MaxRecords 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c4d7c-105">MaxRecords property (ADO)</span></span>
>>>>>>> <span data-ttu-id="c4d7c-106">master</span><span class="sxs-lookup"><span data-stu-id="c4d7c-106">master</span></span>


<span data-ttu-id="c4d7c-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c4d7c-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c4d7c-108">指示通过查询返回到 [Recordset](recordset-object-ado.md) 的最大记录数。</span><span class="sxs-lookup"><span data-stu-id="c4d7c-108">Indicates the maximum number of records to return to a [Recordset](recordset-object-ado.md) from a query.</span></span>

<span data-ttu-id="c4d7c-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="c4d7c-109"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="c4d7c-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="c4d7c-110">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="c4d7c-111">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="c4d7c-111">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="c4d7c-112">master</span><span class="sxs-lookup"><span data-stu-id="c4d7c-112">master</span></span>

<span data-ttu-id="c4d7c-p101">设置或返回一个 **Long** 值，指示要返回的最大记录数。默认值为 0（没有限制）。</span><span class="sxs-lookup"><span data-stu-id="c4d7c-p101">Sets or returns a **Long** value that indicates the maximum number of records to return. Default is zero (no limit).</span></span>

## <a name="remarks"></a><span data-ttu-id="c4d7c-115">备注</span><span class="sxs-lookup"><span data-stu-id="c4d7c-115">Remarks</span></span>

<span data-ttu-id="c4d7c-p102">使用 **MaxRecords** 属性可限制提供程序从数据源返回的记录数。此属性的默认设置为 0，表示提供程序可返回所有请求的记录。</span><span class="sxs-lookup"><span data-stu-id="c4d7c-p102">Use the **MaxRecords** property to limit the number of records that the provider returns from the data source. The default setting of this property is zero, which means the provider returns all requested records.</span></span>

<span data-ttu-id="c4d7c-118">**Recordset** 关闭时 **MaxRecords** 属性为可读/写属性，打开时为只读属性。</span><span class="sxs-lookup"><span data-stu-id="c4d7c-118">The **MaxRecords** property is read/write when the **Recordset** is closed and read-only when it is open.</span></span>

