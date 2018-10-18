---
<span data-ttu-id="e3f5b-101"><<<<<<< 标头标题： DataSource 属性 (ADO) TOCTitle: DataSource 属性 (ADO) === 标题： DataSource 属性 (ADO) TOCTitle: DataSource 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e3f5b-101"><<<<<<< HEAD title: DataSource Property (ADO) TOCTitle: DataSource Property (ADO) ======= title: DataSource property (ADO) TOCTitle: DataSource property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e3f5b-102">母版页 ms:assetid: 5c5d6c9b-b7d4-45a5-0f6a-a5580a74361e ms:mtpsurl: https://msdn.microsoft.com/library/JJ249325(v=office.15) ms:contentKeyID: 48545087 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="e3f5b-102">master ms:assetid: 5c5d6c9b-b7d4-45a5-0f6a-a5580a74361e ms:mtpsurl: https://msdn.microsoft.com/library/JJ249325(v=office.15) ms:contentKeyID: 48545087 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="e3f5b-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="e3f5b-103"><<<<<<< HEAD</span></span>
# <a name="datasource-property-ado"></a><span data-ttu-id="e3f5b-104">DataSource 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e3f5b-104">DataSource Property (ADO)</span></span>
=======
# <a name="datasource-property-ado"></a><span data-ttu-id="e3f5b-105">DataSource 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e3f5b-105">DataSource property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e3f5b-106">master</span><span class="sxs-lookup"><span data-stu-id="e3f5b-106">master</span></span>


<span data-ttu-id="e3f5b-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e3f5b-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e3f5b-108">指示一个对象，其中包含要表示为 [Recordset](recordset-object-ado.md) 对象的数据。</span><span class="sxs-lookup"><span data-stu-id="e3f5b-108">Indicates an object that contains data to be represented as a [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3f5b-109">备注</span><span class="sxs-lookup"><span data-stu-id="e3f5b-109">Remarks</span></span>

<span data-ttu-id="e3f5b-p101">此属性用于使用数据环境创建数据绑定控件。数据环境负责维护数据（数据源）集合，其中包含命名的将用 **Recordset** 对象表示的对象（*数据成员*）*。*</span><span class="sxs-lookup"><span data-stu-id="e3f5b-p101">This property is used to create data-bound controls with the Data Environment. The Data Environment maintains collections of data (data sources) containing named objects (*data members*) that will be represented as a **Recordset** object *.*</span></span>

<span data-ttu-id="e3f5b-112">[DataMember](datamember-property-ado.md) 和 **DataSource** 属性必须一起使用。</span><span class="sxs-lookup"><span data-stu-id="e3f5b-112">The [DataMember](datamember-property-ado.md) and **DataSource** properties must be used in conjunction.</span></span>

<span data-ttu-id="e3f5b-113">所引用的对象必须实现 **IDataSource** 接口，且必须包含 **IRowset** 接口。</span><span class="sxs-lookup"><span data-stu-id="e3f5b-113">The object referenced must implement the **IDataSource** interface and must contain an **IRowset** interface.</span></span>

<span data-ttu-id="e3f5b-114">**用法**</span><span class="sxs-lookup"><span data-stu-id="e3f5b-114">**Usage**</span></span>

```vb
    Dim rs as New ADODB.Recordset
    rs.DataMember = "Command"     'Name of the rowset to bind to
    Set rs.DataSource = myDE      'Name of the object containing an IRowset
```
