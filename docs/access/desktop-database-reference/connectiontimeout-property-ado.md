---
<span data-ttu-id="e260a-101"><<<<<<< 标头标题： ConnectionTimeout 属性 (ADO) TOCTitle: ConnectionTimeout 属性 (ADO) === 标题： ConnectionTimeout 属性 (ADO) TOCTitle: ConnectionTimeout 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e260a-101"><<<<<<< HEAD title: ConnectionTimeout Property (ADO) TOCTitle: ConnectionTimeout Property (ADO) ======= title: ConnectionTimeout property (ADO) TOCTitle: ConnectionTimeout property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e260a-102">母版页 ms:assetid: efc39fd8-afce-5ac0-2fff-cbb55c1a444d ms:mtpsurl: https://msdn.microsoft.com/library/JJ250218(v=office.15) ms:contentKeyID: 48548589 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="e260a-102">master ms:assetid: efc39fd8-afce-5ac0-2fff-cbb55c1a444d ms:mtpsurl: https://msdn.microsoft.com/library/JJ250218(v=office.15) ms:contentKeyID: 48548589 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="e260a-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="e260a-103"><<<<<<< HEAD</span></span>
# <a name="connectiontimeout-property-ado"></a><span data-ttu-id="e260a-104">ConnectionTimeout 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e260a-104">ConnectionTimeout Property (ADO)</span></span>
=======
# <a name="connectiontimeout-property-ado"></a><span data-ttu-id="e260a-105">ConnectionTimeout 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e260a-105">ConnectionTimeout property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e260a-106">master</span><span class="sxs-lookup"><span data-stu-id="e260a-106">master</span></span>


<span data-ttu-id="e260a-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e260a-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e260a-108">指示在建立连接时要等待多长时间才终止连接尝试并生成错误。</span><span class="sxs-lookup"><span data-stu-id="e260a-108">Indicates how long to wait while establishing a connection before terminating the attempt and generating an error.</span></span>

<span data-ttu-id="e260a-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="e260a-109"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="e260a-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="e260a-110">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="e260a-111">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="e260a-111">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="e260a-112">master</span><span class="sxs-lookup"><span data-stu-id="e260a-112">master</span></span>

<span data-ttu-id="e260a-p101">设置或返回一个 **Long** 值，该值指示等待连接打开的时间（以秒为单位）。默认值为 15。</span><span class="sxs-lookup"><span data-stu-id="e260a-p101">Sets or returns a **Long** value that indicates, in seconds, how long to wait for the connection to open. Default is 15.</span></span>

## <a name="remarks"></a><span data-ttu-id="e260a-115">备注</span><span class="sxs-lookup"><span data-stu-id="e260a-115">Remarks</span></span>

<span data-ttu-id="e260a-p102">如果由于网络通信延迟或服务器负载太大而有必要放弃连接尝试，请使用 **Connection** 对象上的 [ConnectionTimeout](connection-object-ado.md) 属性。如果在打开连接前超过了 **ConnectionTimeout** 属性设置的时间，将发生错误，且 ADO 将取消连接尝试。如果将该属性设置为零，ADO 将无限期等待，直到连接打开为止。请确保您向其中写入代码的提供程序支持 **ConnectionTimeout** 功能。</span><span class="sxs-lookup"><span data-stu-id="e260a-p102">Use the **ConnectionTimeout** property on a [Connection](connection-object-ado.md) object if delays from network traffic or heavy server use make it necessary to abandon a connection attempt. If the time from the **ConnectionTimeout** property setting elapses prior to the opening of the connection, an error occurs and ADO cancels the attempt. If you set the property to zero, ADO will wait indefinitely until the connection is opened. Make sure the provider to which you are writing code supports the **ConnectionTimeout** functionality.</span></span>

<span data-ttu-id="e260a-120">**ConnectionTimeout** 属性在连接关闭时为可读/写属性，而在连接打开时为只读属性。</span><span class="sxs-lookup"><span data-stu-id="e260a-120">The **ConnectionTimeout** property is read/write when the connection is closed and read-only when it is open.</span></span>

