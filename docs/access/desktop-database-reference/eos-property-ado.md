---
<span data-ttu-id="e365f-101">标题： EOS 属性 (ADO-访问桌面数据库参考 （英文）)) <<<<<<< 标头 TOCTitle: EOS 属性 (ADO) === TOCTitle: EOS 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e365f-101">title: EOS Property (ADO - Access desktop database reference)) <<<<<<< HEAD TOCTitle: EOS Property (ADO) ======= TOCTitle: EOS property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e365f-102">母版页 ms:assetid: 97cd23ef-cca8-4dcc-2641-082a0e1b853c ms:mtpsurl: https://msdn.microsoft.com/library/JJ249676(v=office.15) ms:contentKeyID: 48546474 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="e365f-102">master ms:assetid: 97cd23ef-cca8-4dcc-2641-082a0e1b853c ms:mtpsurl: https://msdn.microsoft.com/library/JJ249676(v=office.15) ms:contentKeyID: 48546474 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="e365f-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="e365f-103"><<<<<<< HEAD</span></span>
# <a name="eos-property-ado"></a><span data-ttu-id="e365f-104">EOS 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e365f-104">EOS Property (ADO)</span></span>
=======
# <a name="eos-property-ado"></a><span data-ttu-id="e365f-105">EOS 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e365f-105">EOS property (ADO)</span></span>
>>>>>>> <span data-ttu-id="e365f-106">master</span><span class="sxs-lookup"><span data-stu-id="e365f-106">master</span></span>


<span data-ttu-id="e365f-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e365f-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e365f-108">指示当前位置是否位于流的末尾。</span><span class="sxs-lookup"><span data-stu-id="e365f-108">Indicates whether the current position is at the end of the stream.</span></span>

<span data-ttu-id="e365f-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="e365f-109"><<<<<<< HEAD</span></span>
## <a name="return-values"></a><span data-ttu-id="e365f-110">返回值</span><span class="sxs-lookup"><span data-stu-id="e365f-110">Return Values</span></span>
=======
## <a name="return-values"></a><span data-ttu-id="e365f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="e365f-111">Return values</span></span>
>>>>>>> <span data-ttu-id="e365f-112">master</span><span class="sxs-lookup"><span data-stu-id="e365f-112">master</span></span>

<span data-ttu-id="e365f-p101">返回一个 **Boolean** 值，以指示当前位置是否位于流的末尾。如果流中没有更多的字节， **EOS** 将返回 **True** ；如果当前位置后还有字节，它将返回 **False** 。</span><span class="sxs-lookup"><span data-stu-id="e365f-p101">Returns a **Boolean** value that indicates whether the current position is at the end of the stream. **EOS** returns **True** if there are no more bytes in the stream; it returns **False** if there are more bytes following the current position.</span></span>

<span data-ttu-id="e365f-p102">若要设置流位置的末尾位置，请使用 [SetEOS](seteos-method-ado.md) 方法。若要确定当前位置，请使用 [Position](position-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="e365f-p102">To set the end of stream position, use the [SetEOS](seteos-method-ado.md) method. To determine the current position, use the [Position](position-property-ado.md) property.</span></span>

