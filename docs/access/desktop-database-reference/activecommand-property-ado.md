---
<span data-ttu-id="bf7be-101"><<<<<<< 标头标题： ActiveCommand 属性 (ADO) TOCTitle: ActiveCommand 属性 (ADO) ms:assetid: 41c19008-cbf7-ade9-b4ab-e908a16784ac ms:mtpsurl: https://msdn.microsoft.com/library/JJ249190(v=office.15) ms:contentKeyID: 48544459 ms.date: 09/18/2015 mtps_version: v =office.15</span><span class="sxs-lookup"><span data-stu-id="bf7be-101"><<<<<<< HEAD title: ActiveCommand Property (ADO) TOCTitle: ActiveCommand Property (ADO) ms:assetid: 41c19008-cbf7-ade9-b4ab-e908a16784ac ms:mtpsurl: https://msdn.microsoft.com/library/JJ249190(v=office.15) ms:contentKeyID: 48544459 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

# <a name="activecommand-property-ado"></a><span data-ttu-id="bf7be-102">ActiveCommand 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="bf7be-102">ActiveCommand Property (ADO)</span></span>

<span data-ttu-id="bf7be-103">=== 标题： ActiveCommand 属性 (ADO) TOCTitle: ActiveCommand 属性 (ADO) ms:assetid: 41c19008-cbf7-ade9-b4ab-e908a16784ac ms:mtpsurl: https://msdn.microsoft.com/library/JJ249190(v=office.15) ms:contentKeyID: 48544459 ms.date: 10/17/2018 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="bf7be-103">======= title: ActiveCommand property (ADO) TOCTitle: ActiveCommand property (ADO) ms:assetid: 41c19008-cbf7-ade9-b4ab-e908a16784ac ms:mtpsurl: https://msdn.microsoft.com/library/JJ249190(v=office.15) ms:contentKeyID: 48544459 ms.date: 10/17/2018 mtps_version: v=office.15</span></span>
---

# <a name="activecommand-property-ado"></a><span data-ttu-id="bf7be-104">ActiveCommand 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="bf7be-104">ActiveCommand property (ADO)</span></span>
>>>>>>> <span data-ttu-id="bf7be-105">master</span><span class="sxs-lookup"><span data-stu-id="bf7be-105">master</span></span>

<span data-ttu-id="bf7be-106">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="bf7be-106">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="bf7be-107">指示创建关联的 [Recordset](command-object-ado.md) 对象的 [Command](recordset-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="bf7be-107">Indicates the [Command](command-object-ado.md) object that created the associated [Recordset](recordset-object-ado.md) object.</span></span>

<span data-ttu-id="bf7be-108"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="bf7be-108"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="bf7be-109">返回值</span><span class="sxs-lookup"><span data-stu-id="bf7be-109">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="bf7be-110">返回值</span><span class="sxs-lookup"><span data-stu-id="bf7be-110">Return value</span></span>
>>>>>>> <span data-ttu-id="bf7be-111">master</span><span class="sxs-lookup"><span data-stu-id="bf7be-111">master</span></span>

<span data-ttu-id="bf7be-p101">返回一个包含 **Command** 对象的 **Variant** 。默认值为一个空对象引用。</span><span class="sxs-lookup"><span data-stu-id="bf7be-p101">Returns a **Variant** that contains a **Command** object. Default is a null object reference.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf7be-114">备注</span><span class="sxs-lookup"><span data-stu-id="bf7be-114">Remarks</span></span>

<span data-ttu-id="bf7be-115">**ActiveCommand** 为只读属性。</span><span class="sxs-lookup"><span data-stu-id="bf7be-115">The **ActiveCommand** property is read-only.</span></span>

<span data-ttu-id="bf7be-116"><<<<<<< 标头如果**Command**对象不用于创建当前的**记录集**，则返回一个**Null**对象引用。</span><span class="sxs-lookup"><span data-stu-id="bf7be-116"><<<<<<< HEAD If a **Command** object was not used to create the current **Recordset**, then a **Null** object reference is returned.</span></span>
<span data-ttu-id="bf7be-117">=== 如果**Command**对象不用于创建当前的**记录集**，则返回一个**Null**对象引用。</span><span class="sxs-lookup"><span data-stu-id="bf7be-117">======= If a **Command** object was not used to create the current **Recordset**, a **Null** object reference is returned.</span></span>
>>>>>>> <span data-ttu-id="bf7be-118">master</span><span class="sxs-lookup"><span data-stu-id="bf7be-118">master</span></span>

<span data-ttu-id="bf7be-119">当仅给定了生成的 **Recordset** 对象时，可以使用此属性来查找关联的 **Command** 对象。</span><span class="sxs-lookup"><span data-stu-id="bf7be-119">Use this property to find the associated **Command** object when you are given only the resulting **Recordset** object.</span></span>

