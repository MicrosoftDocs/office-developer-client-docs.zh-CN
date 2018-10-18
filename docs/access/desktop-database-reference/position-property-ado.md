---
<span data-ttu-id="617c5-101"><<<<<<< 标头标题： Position 属性 (ADO) TOCTitle: Position 属性 (ADO) === 标题： Position 属性 (ADO) TOCTitle: Position 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="617c5-101"><<<<<<< HEAD title: Position Property (ADO) TOCTitle: Position Property (ADO) ======= title: Position property (ADO) TOCTitle: Position property (ADO)</span></span>
>>>>>>> <span data-ttu-id="617c5-102">母版页 ms:assetid: a07c9197-673b-ddf2-fca9-b0b54fbd67b4 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249738(v=office.15) ms:contentKeyID: 48546709 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="617c5-102">master ms:assetid: a07c9197-673b-ddf2-fca9-b0b54fbd67b4 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249738(v=office.15) ms:contentKeyID: 48546709 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="617c5-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="617c5-103"><<<<<<< HEAD</span></span>
# <a name="position-property-ado"></a><span data-ttu-id="617c5-104">Position 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="617c5-104">Position Property (ADO)</span></span>
=======
# <a name="position-property-ado"></a><span data-ttu-id="617c5-105">Position 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="617c5-105">Position property (ADO)</span></span>
>>>>>>> <span data-ttu-id="617c5-106">master</span><span class="sxs-lookup"><span data-stu-id="617c5-106">master</span></span>


<span data-ttu-id="617c5-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="617c5-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="617c5-108">指示 [Stream](stream-object-ado.md) 对象中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="617c5-108">Indicates the current position within a [Stream](stream-object-ado.md) object.</span></span>

<span data-ttu-id="617c5-109"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="617c5-109"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="617c5-110">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="617c5-110">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="617c5-111">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="617c5-111">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="617c5-112">master</span><span class="sxs-lookup"><span data-stu-id="617c5-112">master</span></span>

<span data-ttu-id="617c5-p101">设置或返回一个 **Long** 值，指定当前位置从流开始处的偏移量（以字节为单位）。默认值为 0，表示流中的第一个字节。</span><span class="sxs-lookup"><span data-stu-id="617c5-p101">Sets or returns a **Long** value that specifies the offset, in number of bytes, of the current position from the beginning of the stream. The default is 0, which represents the first byte in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="617c5-115">备注</span><span class="sxs-lookup"><span data-stu-id="617c5-115">Remarks</span></span>

<span data-ttu-id="617c5-p102">当前位置可移至流末尾之后的某点。如果在流末尾之后指定当前位置，则 [Stream](https://msdn.microsoft.com/library/jj250128\(v=office.15\)) 对象的 **Size** 也将相应增加。按这种方法添加的任何新字节均将为空。</span><span class="sxs-lookup"><span data-stu-id="617c5-p102">The current position can be moved to a point after the end of the stream. If you specify the current position beyond the end of the stream, the [Size](https://msdn.microsoft.com/library/jj250128\(v=office.15\)) of the **Stream** object will be increased accordingly. Any new bytes added in this way will be null.</span></span>


> [!NOTE]
> <P><span data-ttu-id="617c5-p103">[!注释] <STRONG>Position</STRONG> 始终以字节为单位。对于使用多字节字符集的文本流，将位置值乘以字符大小可确定字符编号。例如，对于双字节字符集，第一个字符处于位置 0，第二个字符处于位置 2，第三个字符处于位置 4，依此类推。</span><span class="sxs-lookup"><span data-stu-id="617c5-p103"><STRONG>Position</STRONG> always measures bytes. For text streams using multibyte character sets, multiply the position by the character size to determine the character number. For example, for a two-byte character set, the first character is at position 0, the second character at position 2, the third character at position 4, and so on.</span></span></P>



<span data-ttu-id="617c5-p104">不能使用负值更改 **Stream** 中的当前位置。只有整数可用于 **Position** 。</span><span class="sxs-lookup"><span data-stu-id="617c5-p104">Negative values cannot be used to change the current position in a **Stream**. Only positive numbers can be used for **Position**.</span></span>

<span data-ttu-id="617c5-p105">对于只读 **Stream** 对象，如果将 **Position** 设置为大于 **Stream** 的 **Size** 的值，则 ADO 不会返回错误。这样并不会更改 **Stream** 的大小，也不会以任何方式改变 **Stream** 的内容。但是，由于会导致无意义的 **Position** 值，因此应避免这样做。</span><span class="sxs-lookup"><span data-stu-id="617c5-p105">For read-only **Stream** objects, ADO will not return an error if **Position** is set to a value greater than the **Size** of the **Stream**. This does not change the size of the **Stream**, or alter the **Stream** contents in any way. However, doing this should be avoided because it results in a meaningless **Position** value.</span></span>

