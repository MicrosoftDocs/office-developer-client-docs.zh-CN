---
<span data-ttu-id="29a6a-101"><<<<<<< 标头标题： DataMember 属性 (ADO) TOCTitle: DataMember 属性 (ADO) === 标题： DataMember 属性 (ADO) TOCTitle: DataMember 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="29a6a-101"><<<<<<< HEAD title: DataMember Property (ADO) TOCTitle: DataMember Property (ADO) ======= title: DataMember property (ADO) TOCTitle: DataMember property (ADO)</span></span>
>>>>>>> <span data-ttu-id="29a6a-102">母版页 ms:assetid: f89e1d42-7993-764b-4e8a-2f449903f792 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250263(v=office.15) ms:contentKeyID: 48548787 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="29a6a-102">master ms:assetid: f89e1d42-7993-764b-4e8a-2f449903f792 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250263(v=office.15) ms:contentKeyID: 48548787 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="29a6a-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="29a6a-103"><<<<<<< HEAD</span></span>
# <a name="datamember-property-ado"></a><span data-ttu-id="29a6a-104">DataMember 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="29a6a-104">DataMember Property (ADO)</span></span>
=======
# <a name="datamember-property-ado"></a><span data-ttu-id="29a6a-105">DataMember 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="29a6a-105">DataMember property (ADO)</span></span>
>>>>>>> <span data-ttu-id="29a6a-106">master</span><span class="sxs-lookup"><span data-stu-id="29a6a-106">master</span></span>

<span data-ttu-id="29a6a-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="29a6a-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="29a6a-108">指示将从 [DataSource](datasource-property-ado.md) 属性所引用的对象中检索的数据成员的名称。</span><span class="sxs-lookup"><span data-stu-id="29a6a-108">Indicates the name of the data member that will be retrieved from the object referenced by the [DataSource](datasource-property-ado.md) property.</span></span>

<span data-ttu-id="29a6a-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="29a6a-109"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="29a6a-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="29a6a-110">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="29a6a-111">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="29a6a-111">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="29a6a-112">master</span><span class="sxs-lookup"><span data-stu-id="29a6a-112">master</span></span>

<span data-ttu-id="29a6a-p101">设置或返回一个 **String** 值。该名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="29a6a-p101">Sets or returns a **String** value. The name is not case sensitive.</span></span>

## <a name="remarks"></a><span data-ttu-id="29a6a-115">备注</span><span class="sxs-lookup"><span data-stu-id="29a6a-115">Remarks</span></span>

<span data-ttu-id="29a6a-p102">此属性用于使用数据环境创建数据绑定控件。数据环境负责维护数据（数据源）集合，其中包含命名的将用 [Recordset](recordset-object-ado.md) 对象表示的对象（*数据成员*）*。*</span><span class="sxs-lookup"><span data-stu-id="29a6a-p102">This property is used to create data-bound controls with the Data Environment. The Data Environment maintains collections of data (data sources) containing named objects (*data members*) that will be represented as a [Recordset](recordset-object-ado.md) object *.*</span></span>

<span data-ttu-id="29a6a-118">**DataMember** 和 **DataSource** 属性必须一起使用。</span><span class="sxs-lookup"><span data-stu-id="29a6a-118">The **DataMember** and **DataSource** properties must be used in conjunction.</span></span>

<span data-ttu-id="29a6a-p103">**DataMember** 属性确定 **DataSource** 属性指定的哪个对象将用 **Recordset** 对象表示。设置此属性之前，相应的 **Recordset** 对象必须为关闭状态。如果 **DataMember** 属性未在 **DataSource** 属性之前设置，或者如果 **DataSource** 中指定的对象不能识别 **DataMember** 名称，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="29a6a-p103">The **DataMember** property determines which object specified by the **DataSource** property will be represented as a **Recordset** object. The **Recordset** object must be closed before this property is set. An error is generated if the **DataMember** property isn't set before the **DataSource** property, or if the **DataMember** name isn't recognized by the object specified in the **DataSource** property.</span></span>

<span data-ttu-id="29a6a-122">**用法**</span><span class="sxs-lookup"><span data-stu-id="29a6a-122">**Usage**</span></span>

```vb
    Dim rs as New ADODB.Recordset
    rs.DataMember = "Command"     'Name of the rowset to bind to
    Set rs.DataSource = myDE      'Name of the object containing an IRowset
```
