---
<span data-ttu-id="51668-101"><<<<<<< 标头标题： StayInSync 属性 (ADO) TOCTitle: StayInSync 属性 (ADO) === 标题： StayInSync 属性 (ADO) TOCTitle: StayInSync 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="51668-101"><<<<<<< HEAD title: StayInSync Property (ADO) TOCTitle: StayInSync Property (ADO) ======= title: StayInSync property (ADO) TOCTitle: StayInSync property (ADO)</span></span>
>>>>>>> <span data-ttu-id="51668-102">母版页 ms:assetid: 02c95c10-4032-14e1-e506-f334a8787142 ms:mtpsurl: https://msdn.microsoft.com/library/JJ248792(v=office.15) ms:contentKeyID: 48542966 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="51668-102">master ms:assetid: 02c95c10-4032-14e1-e506-f334a8787142 ms:mtpsurl: https://msdn.microsoft.com/library/JJ248792(v=office.15) ms:contentKeyID: 48542966 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="51668-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="51668-103"><<<<<<< HEAD</span></span>
# <a name="stayinsync-property-ado"></a><span data-ttu-id="51668-104">StayInSync 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="51668-104">StayInSync Property (ADO)</span></span>
=======
# <a name="stayinsync-property-ado"></a><span data-ttu-id="51668-105">StayInSync 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="51668-105">StayInSync property (ADO)</span></span>
>>>>>>> <span data-ttu-id="51668-106">master</span><span class="sxs-lookup"><span data-stu-id="51668-106">master</span></span>


<span data-ttu-id="51668-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="51668-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="51668-108">指示在分层 [Recordset](recordset-object-ado.md) 对象中，当父行位置更改时，对基础子记录（即*章节*）的引用是否发生了更改。</span><span class="sxs-lookup"><span data-stu-id="51668-108">Indicates, in a hierarchical [Recordset](recordset-object-ado.md) object, whether the reference to the underlying child records (that is, the *chapter*) changes when the parent row position changes.</span></span>

<span data-ttu-id="51668-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="51668-109"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="51668-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="51668-110">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="51668-111">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="51668-111">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="51668-112">master</span><span class="sxs-lookup"><span data-stu-id="51668-112">master</span></span>

<span data-ttu-id="51668-113">设置或返回一个**布尔**值。</span><span class="sxs-lookup"><span data-stu-id="51668-113">Sets or returns a **Boolean** value.</span></span> <span data-ttu-id="51668-114">默认值为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="51668-114">The default value is **True**.</span></span> <span data-ttu-id="51668-115">如果 **，则返回 True**，章将更新的父**Recordset**对象更改的行位置; 如果如果**False**，章将继续即使父**Recordset**对象已更改行位置，请参阅上一章中的数据。</span><span class="sxs-lookup"><span data-stu-id="51668-115">If **True**, the chapter will be updated if the parent **Recordset** object changes row position; if **False**, the chapter will continue to refer to data in the previous chapter even though the parent **Recordset** object has changed row position.</span></span>

## <a name="remarks"></a><span data-ttu-id="51668-116">备注</span><span class="sxs-lookup"><span data-stu-id="51668-116">Remarks</span></span>

<span data-ttu-id="51668-p102">此属性应用于分级 Recordset，例如由 [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) 提供的记录集，而且必须先在父 **Recordset** 上设置才能检索子 **Recordset** 。此属性简化了分级记录集的导航操作。</span><span class="sxs-lookup"><span data-stu-id="51668-p102">This property applies to hierarchical Recordsets, such as those supported by the [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md), and must be set on the parent **Recordset** before the child **Recordset** is retrieved. This property simplifies navigating hierarchical recordsets.</span></span>

