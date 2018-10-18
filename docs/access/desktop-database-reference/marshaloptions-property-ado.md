---
<span data-ttu-id="e1cde-101"><<<<<<< 标头标题： MarshalOptions 属性 (ADO) TOCTitle: MarshalOptions 属性 (ADO) === 标题： MarshalOptions 属性 (ADO) TOCTitle: MarshalOptions 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e1cde-101"><<<<<<< HEAD title: MarshalOptions Property (ADO) TOCTitle: MarshalOptions Property (ADO) ======= title: MarshalOptions property (ADO) TOCTitle: MarshalOptions property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e1cde-102">母版页 ms:assetid: dc9c4e94-0725-210d-8251-079054541142 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250118(v=office.15) ms:contentKeyID: 48548143 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="e1cde-102">master ms:assetid: dc9c4e94-0725-210d-8251-079054541142 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250118(v=office.15) ms:contentKeyID: 48548143 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="e1cde-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="e1cde-103"><<<<<<< HEAD</span></span>
# <a name="marshaloptions-property-ado"></a><span data-ttu-id="e1cde-104">MarshalOptions 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e1cde-104">MarshalOptions Property (ADO)</span></span>
=======
# <a name="marshaloptions-property-ado"></a><span data-ttu-id="e1cde-105">MarshalOptions 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e1cde-105">MarshalOptions property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e1cde-106">master</span><span class="sxs-lookup"><span data-stu-id="e1cde-106">master</span></span>


<span data-ttu-id="e1cde-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e1cde-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e1cde-108">指示哪些记录要封送回服务器。</span><span class="sxs-lookup"><span data-stu-id="e1cde-108">Indicates which records are to be marshaled back to the server.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="e1cde-109">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="e1cde-109">Settings And Return Values</span></span>

<span data-ttu-id="e1cde-p101">设置或返回一个 [MarshalOptionsEnum](marshaloptionsenum.md) 值。默认值是 **adMarshalAll** 。</span><span class="sxs-lookup"><span data-stu-id="e1cde-p101">Sets or returns a [MarshalOptionsEnum](marshaloptionsenum.md) value. The default value is **adMarshalAll**.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1cde-112">备注</span><span class="sxs-lookup"><span data-stu-id="e1cde-112">Remarks</span></span>

<span data-ttu-id="e1cde-113"><<<<<<< 标头时使用客户端[Recordset](recordset-object-ado.md)，客户端已修改的记录写入回中间层或通过称为封送，打包和发送接口的过程的技术的 Web 服务器跨线程或进程边界方法参数。</span><span class="sxs-lookup"><span data-stu-id="e1cde-113"><<<<<<< HEAD When using a client-side [Recordset](recordset-object-ado.md), records that have been modified on the client are written back to the middle tier or Web server through a technique called marshaling, the process of packaging and sending interface method parameters across thread or process boundaries.</span></span> <span data-ttu-id="e1cde-114">当已修改的远程数据通过封送更新回中间层或 Web 服务器时，设置 **MarshalOptions** 属性可提高性能。</span><span class="sxs-lookup"><span data-stu-id="e1cde-114">Setting the **MarshalOptions** property can improve performance when modified remote data is marshaled for updating back to the middle tier or Web server.</span></span>
<span data-ttu-id="e1cde-115">=== 时使用的客户端[Recordset](recordset-object-ado.md)，客户端已修改的记录写入回中间层或通过称为封送，打包和发送跨接口方法参数的过程的技术的 web 服务器线程或进程的边界。</span><span class="sxs-lookup"><span data-stu-id="e1cde-115">======= When using a client-side [Recordset](recordset-object-ado.md), records that have been modified on the client are written back to the middle tier or web server through a technique called marshaling, the process of packaging and sending interface method parameters across thread or process boundaries.</span></span> <span data-ttu-id="e1cde-116">已修改的远程数据封送回中间层或 web 服务器更新时，设置**MarshalOptions**属性可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="e1cde-116">Setting the **MarshalOptions** property can improve performance when modified remote data is marshaled for updating back to the middle tier or web server.</span></span>
>>>>>>> <span data-ttu-id="e1cde-117">master</span><span class="sxs-lookup"><span data-stu-id="e1cde-117">master</span></span>

<span data-ttu-id="e1cde-118">**远程数据服务用法**此属性只能在客户端**Recordset**上使用。</span><span class="sxs-lookup"><span data-stu-id="e1cde-118">**Remote Data Service Usage**This property is used only on a client-side **Recordset**.</span></span>

